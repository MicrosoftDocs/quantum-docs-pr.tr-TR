---
title: Q# programlarını test etme ve hata ayıklama
description: Kuantum programlarını test etmek ve hata ayıklamak için birim testlerini, olguları ve iddiaları ve döküm işlevlerini nasıl kullanacağınızı öğrenin.
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: caf15b7273b7efed1da87a2edd62c06cd4357593
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030591"
---
# <a name="testing-and-debugging"></a>Test ve Hata Ayıklama

Klasik programlamada olduğu gibi, kuantum programlarının amaçlandığı gibi hareket ettiğini kontrol edebilmek ve yanlış olan bir kuantum programını tanılayabilmek esastır.
Bu bölümde, kuantum programlarını test etmek ve hata ayıklamak için Q# tarafından sunulan araçları kapsamaktayız.

## <a name="unit-tests"></a>Ünite Testleri

Klasik programları sınamak için yaygın bir yaklaşım, bir kitaplıkta kod çalıştıran *birim testleri* adı verilen küçük programlar yazmak ve çıktısını beklenen bazı çıktılarla karşılaştırmaktır.
Örneğin, *biz bir priori* `4`bildiğimiz `Square(2)` için, bu döner sağlamak isteyebilirsiniz $ 2 ^2 = 4 $.

Q#, kuantum programları için birim testler oluşturmayı destekler ve [xUnit](https://xunit.github.io/) birim test çerçevesi içinde test olarak yürütülebilir.

### <a name="creating-a-test-project"></a>Test Projesi Oluşturma

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Görsel Stüdyo 2019'u açın. `File` Menüye gidin ve `New`seçin.  >  `Project...`
Sağ üst köşede şablonu `Q#` `Q# Test Project` arayın ve seçin.

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

Sık kullanılan komut satırından aşağıdaki komutu çalıştırın:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Yeni projenizde, yeni `Tests.qs`Q# birim testlerini tanımlamak için uygun bir yer sağlayan tek bir dosya olacaktır.
Başlangıçta bu dosya, yeni `AllocateQubit` tahsis edilen bir qubit'in $\ket{0}$ durumunda olduğunu denetleyen ve bir iletiyi yazdıran bir örnek birim testi içerir:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

:yeni: Tür `Unit` ve döndürme `Unit` bağımsız değişkeni alan herhangi bir Q# `@Test("...")` işlemi veya işlevi öznitelik üzerinden birim testi olarak işaretlenebilir. Bu öznitelik için `"QuantumSimulator"` argüman, yukarıda, test yürütüldedilir hedef belirtir. Tek bir test birden çok hedefüzerinde yürütülebilir. Örneğin, yukarıdaki `AllocateQubit`bir `@Test("ResourcesEstimator")` öznitelik ekleyin. 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Dosyayı kaydedin ve tüm testleri çalıştırın. Şimdi iki birim testleri olmalıdır, biri AllocateQubit QuantumSimulator üzerinde yürütülür, ve bir nerede ResourceEstimator yürütülür. 

Q# derleyicisi yerleşik hedefleri tanır "QuantumSimulator", "ToffoliSimulator" ve "ResourcesEstimator" birim testleri için geçerli yürütme hedefleri olarak. Özel bir yürütme hedefi tanımlamak için tam nitelikli bir ad belirtmek de mümkündür. 

### <a name="running-q-unit-tests"></a>Koşu Q# Birim Testleri

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Çözüm başına tek seferlik kurulum olarak, `Test` menüye gidin ve seçin. `Test Settings`  >  `Default Processor Architecture`  >  `X64`

> [!TIP]
> Visual Studio için varsayılan işlemci mimarisi ayarı,`.suo`her çözüm için çözüm seçenekleri ( ) dosyasında depolanır.
> Bu dosyayı silerseniz, işlemci `X64` mimariniz olarak yeniden seçmeniz gerekir.

Projeyi `Test` oluşturun, menüye gidin `Windows`  >  `Test Explorer`ve seçin. `AllocateQubit``Not Run Tests` gruptaki testler listesinde gösterecektir. Bu `Run All` bireysel testi seçin veya çalıştırın ve geçmesi gerekir!

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

Testleri çalıştırmak için proje klasörüne (klasör) `Tests.csproj`gidin ve komutu çalıştırın:

```bash
$ dotnet restore
$ dotnet test
```

Aşağıdakilere benzer çıktı almalısınız:

```
Build started, please wait...
Build completed.

Test run for C:\Users\chgranad.REDMOND\tmp\Tests\bin\Debug\netcoreapp2.0\Tests.dll(.NETCoreApp,Version=v2.0)
Microsoft (R) Test Execution Command Line Tool Version 15.3.0-preview-20170628-02
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.5864002]   Discovering: Tests
[xUnit.net 00:00:00.7073844]   Discovered:  Tests
[xUnit.net 00:00:00.7453826]   Starting:    Tests
[xUnit.net 00:00:00.9590439]   Finished:    Tests

Total tests: 1. Passed: 1. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.9607 Seconds
```

Birim testleri adlarına ve/veya yürütme hedefine göre filtrelenebilir:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

İçsel işlev <xref:microsoft.quantum.intrinsic.message> türüne `(String -> Unit)` sahiptir ve tanılama iletilerinin oluşturulmasını sağlar.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Test Gezgini'nde bir test çalıştırDıktan ve teste tıkladıktan sonra, test yürütmesi hakkında bilgi içeren bir panel görünür: Geçirilen/Başarısız olan durum, geçen süre ve bir "Çıktı" bağlantısı. "Çıktı" bağlantısını tıklattığınızda, test çıktısı yeni bir pencerede açılır.

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

Her testin geçme/başarısız durumu konsola `dotnet test`.
Başarısız testler için çıktılar da başarısızlığı tanılamaya yardımcı olmak için konsola yazdırılır.

***

## <a name="facts-and-assertions"></a>Gerçekler ve İddialar

Q# işlevlerinin _mantıksal_ yan etkileri olmadığından, çıkış türü boş olan bir işlevi yürütmenin _diğer_ `()` etkileri hiçbir zaman Q# programı içinde gözlemlenmez.
Diğer bir diğer, bir hedef makine, bu `()` ihmalin aşağıdaki Q# kodunun davranışını değiştirmeyeceğini garanti ederek dönen herhangi bir işlevi yürütmemeyi seçebilir.
Bu, dönen `()` işlevleri `Unit`(yani) iddiaları katıştırma ve mantık hata ayıklama için yararlı bir araç yapar. 

Basit bir örnek ele alalım:

```qsharp
function PositivityFact(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Burada, anahtar `fail` kelime hesaplama devam etmemelidir gösterir, Q # programı çalıştıran hedef makinede bir özel durum yükselterek.
Tanım olarak, bir deyim ebeden sonra başka Bir Q# kodu çalıştırılmadığı için, Bu tür bir `fail` hata Q#'ın içinden gözlemlenemez.
Bu nedenle, bir çağrının `PositivityFact`ötesine geçersek, girişinin olumlu olduğundan emin olabilirsiniz.

Ad alanından `PositivityFact` [`Fact`](xref:microsoft.quantum.diagnostics.fact) işlevi kullanarak aynı davranışı uygulayabileceğimizi <xref:microsoft.quantum.diagnostics> unutmayın:

```qsharp
    Fact(value > 0, "Expected a positive number.");
```

*İddialar,* diğer taraftan, gerçeklere benzer şekilde kullanılır, ancak hedef makinenin durumuna bağlı olabilir. Buna karşılık, bunlar operasyon olarak tanımlanırken, olgular işlevler (yukarıdaki gibi) olarak tanımlanır.
Ayrımı anlamak için, bir iddia içinde bir gerçeğin aşağıdaki kullanımını göz önünde bulundurun:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Burada, kullanabileceğimiz qubit sayısını döndürmek için işlemi <xref:microsoft.quantum.environment.getqubitsavailabletouse> kullanıyoruz.
Bu açıkça programın küresel durumuna ve yürütme ortamına `AssertQubitsAreAvailable` bağlı olduğu için, bizim tanımımız da bir operasyon olmalıdır.
Ancak, bu küresel `Bool` `Fact` durumu, işleve girdi olarak basit bir değer sağlamak için kullanabiliriz.

Bu fikirler üzerine bina, [prelüd](xref:microsoft.quantum.libraries.standard.prelude) iki özellikle <xref:microsoft.quantum.intrinsic.assert> <xref:microsoft.quantum.intrinsic.assertprob> yararlı iddialar sunuyor, `()`ve her ikisi de üzerine operasyon olarak modellenmiştir. Bu iddiaların her biri, belirli bir ilgi ölçüsünü, ölçümün yapılacağı kuantum kaydını ve varsayımsal bir sonucu açıklayan bir Pauli operatöralır.
Simülasyon ile çalışan hedef makinelerde, [klonlamasız teoremi](https://en.wikipedia.org/wiki/No-cloning_theorem)ile bağlı değiliz ve bu tür iddialara aktarılan kaydı bozmadan bu ölçümleri gerçekleştirebiliyoruz.
Bir simülatör daha sonra, yukarıdaki `PositivityFact` fonksiyona benzer, varsayımsal sonuç pratikte gözlenen olmaz eğer hesaplama iptal edebilirsiniz:

```qsharp
using (register = Qubit()) 
{
    H(register);
    Assert([PauliX], [register], Zero);
    // Even though we do not have access to states in Q#,
    // we know by the anthropic principle that the state
    // of register at this point is |+〉.
}
```

Fiziksel kuantum donanım, nerede no-klonlama teoremi kuantum durumunun `Assert` incelenmesini engeller, ve `AssertProb` işlemler sadece başka bir etkisi ile dönmek. `()`

Ad <xref:microsoft.quantum.diagnostics> alanı bize daha gelişmiş `Assert` koşulları kontrol etmek için izin ailenin birkaç daha fazla işlevleri sağlar. 

## <a name="dump-functions"></a>Döküm Fonksiyonları

Kuantum programlarını sorun gidermeye <xref:microsoft.quantum.diagnostics> yardımcı olmak için, ad alanı bir dosyaya hedef <xref:microsoft.quantum.diagnostics.dumpmachine> makinenin geçerli durumunu dökümü iki işlev sunar: ve <xref:microsoft.quantum.diagnostics.dumpregister>. Her birinin üretilen çıktısı hedef makineye bağlıdır.

### <a name="dumpmachine"></a>DumpMachine

Kuantum Gelişim Kiti'nin bir parçası olarak dağıtılan tam devlet kuantum simülatörü dosyaya tüm kuantum sisteminin [dalga fonksiyonunu,](https://en.wikipedia.org/wiki/Wave_function) karmaşık sayıların tek boyutlu bir dizi olarak yazar, her öğe hesaplamasal temel durumu ölçme olasılığının genliğini temsil eder $\ket{n}$, burada $ket{n} = \ket{b_{n-n}... b_1b_0}$ bit için\{\}$ b_i $. Örneğin, yalnızca iki qubit ayrılmış bir makinede ve kuantum durumunda $$ \begin{align}{1}\ket{\psi} ={2}\frac{00} {\sqrt } \ket{2} -{10}\frac{(1 + <xref:microsoft.quantum.diagnostics.dumpmachine> i)} \ket , \end{align} $$ arama bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

İlk satır, ilgili qubit'lerin kimliklerini önemli sırayla içeren bir yorum sağlar.
Satırların geri kalanı, kartezyen ve kutupbiçimlerinde $\ket{n}$ temel durum vektörünün ölçülmesi nin olasılık genliğini açıklar. İlk satır için ayrıntılı olarak:

* **`∣0❭:`** bu satır `0` hesaplama temel durumuna karşılık gelir
* **`0.707107 +  0.000000 i`**: Kartezyen formatında olasılık genliği.
* **` == `**: `equal` işaret her iki eşdeğer temsili de ayırıyor.
* **`**********  `**: Büyüklüğün grafiksel gösterimi, `*` sayısı bu durum vektörünün ölçülmesi olasılığı ile orantılıdır.
* **`[ 0.500000 ]`**: büyüklüğün sayısal değeri
* **`    ---`**: Genlik evresinin grafiksel gösterimi (aşağıya bakınız).
* **`[ 0.0000 rad ]`**: fazın sayısal değeri (radyanlarda).

Hem büyüklük hem de faz grafik gösterimi ile görüntülenir. Büyüklük gösterimi doğrudan ileri: bir çubuk `*`gösterir , büyük olasılık bar olacak. Faz için, aralıklara dayalı açıyı temsil edecek aşağıdaki sembolleri gösteririz:

```
[ -π/16,   π/16)       ---
[  π/16,  3π/16)        /-
[ 3π/16,  5π/16)        / 
[ 5π/16,  7π/16)       +/ 
[ 7π/16,  9π/16)      ↑   
[ 8π/16, 11π/16)    \-    
[ 7π/16, 13π/16)    \     
[ 7π/16, 15π/16)   +\     
[15π/16, 19π/16)   ---    
[17π/16, 19π/16)   -/     
[19π/16, 21π/16)    /     
[21π/16, 23π/16)    /+    
[23π/16, 25π/16)      ↓   
[25π/16, 27π/16)       -\ 
[27π/16, 29π/16)        \ 
[29π/16, 31π/16)        \+
[31π/16,   π/16)       ---
```

Aşağıdaki örnekler `DumpMachine` bazı ortak durumlar için gösterilmektedir:

### `∣0❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

### `∣1❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣1❭:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
```

### `∣+❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
```

### `∣-❭`

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]      --- [  0.00000 rad ]
∣1❭:    -0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]  ---     [  3.14159 rad ]
```


  > [!NOTE]
  > Bir qubit id runtime atanır ve mutlaka qubit tahsis edildiği sırayla veya bir qubit kayıt içinde konumu ile uyumlu değildir.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Visual Studio'da kodunuza bir kesme noktası koyarak ve bir qubit değişkeninin değerini inceleyerek bir qubit id'i çözebilirsiniz, örneğin:
  > 
  > ![Visual Studio'da qubit id göster](~/media/qubit_id.png)
  >
  > `0` indeksi olan `register2` qubit`3`id= , dizinli `1` `2`qubit id= .

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > <xref:microsoft.quantum.intrinsic.message> İşlevi kullanarak ve iletideki qubit değişkenini geçerek bir qubit id'i çözebilirsiniz, örneğin:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > bu çıktıyı oluşturabilir:
  >```
  > 0=q:3; 1=q:2
  >```
  > yani `0` dizin li qubit `register2` id=`3`, dizinli `1` qubit`2`id= .


***

<xref:microsoft.quantum.diagnostics.dumpmachine>ad alanının <xref:microsoft.quantum.diagnostics> bir parçasıdır, bu nedenle kullanmak için `open` bir deyim eklemeniz gerekir:

```qsharp
namespace Samples {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {
        using (qubits = Qubit[2]) {
            H(qubits[1]);
            DumpMachine("dump.txt");
        }
    }
}
```


### <a name="dumpregister"></a>DumpRegister

<xref:microsoft.quantum.diagnostics.dumpregister>gibi <xref:microsoft.quantum.diagnostics.dumpmachine>çalışır , aynı zamanda sadece ilgili qubits ile ilgili bilgi miktarını sınırlamak için qubits bir dizi alır dışında.

Olduğu <xref:microsoft.quantum.diagnostics.dumpmachine>gibi , tarafından <xref:microsoft.quantum.diagnostics.dumpregister> oluşturulan bilgiler hedef makineye bağlıdır. Tam hal kuantum simülatörü için dosyaya dalga fonksiyonu kadar kuantum alt sisteminin küresel bir faz olarak aynı formatta sağlanan qubits tarafından oluşturulan yazar <xref:microsoft.quantum.diagnostics.dumpmachine>.  Örneğin, sadece iki{1}qubit ayrılmış bir makine almak ve kuantum durumunda $$ \begin{align} \ket{\psi} ={2}\frac{00} {\sqrt } \ket{2} -{10} \frac{(1 + i)} \ket{1}= e^{-i\pi/4 } ( (\frac {\sqrt{2}} \ket{0} - \frac{(1 + i)}{2} \ket{1} ) \otimes \frac{-(1 + i)}{\sqrt{2}} \ket){0} , \end{align} $$ arama <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

ve <xref:microsoft.quantum.diagnostics.dumpregister> bu `qubit[1]` çıktıyı oluşturmak için çağrı:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Genel olarak, başka bir kayıtla dolaşmış bir kaydın durumu, saf bir durumdan çok karışık bir durumdur. Bu durumda, <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi çıktırın:

```
Qubits provided (0;) are entangled with some other qubit.
```

Aşağıdaki örnek, her ikisini de <xref:microsoft.quantum.diagnostics.dumpregister> <xref:microsoft.quantum.diagnostics.dumpmachine> ve Q# kodunuzda nasıl kullanabileceğinizi gösterir:

```qsharp
namespace app
{
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;

    operation Operation () : Unit {

        using (qubits = Qubit[2]) {
            X(qubits[1]);
            H(qubits[1]);
            R1Frac(1, 2, qubits[1]);
            
            DumpMachine("dump.txt");
            DumpRegister("q0.txt", qubits[0..0]);
            DumpRegister("q1.txt", qubits[1..1]);

            ResetAll(qubits);
        }
    }
}
```

## <a name="debugging"></a>Hata ayıklama

`Assert` Üstüne ve `Dump` işlevleri ve işlemleri, Q # standart Visual Studio hata ayıklama yetenekleri bir alt kümesi destekler: satır kesme noktaları [ayarlama,](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints) [F10 kullanarak kod üzerinden adım](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) ve klasik [değişkenlerin değerlerini inceleyerek](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) simülatörde kod yürütme sırasında tüm mümkündür.

Visual Studio Code hata ayıklama OmniSharp tarafından desteklenen Visual Studio Code uzantısı için C # tarafından sağlanan hata ayıklama yetenekleri yararlanır ve [en son sürümünü](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)yüklemeyi gerektirir. 
