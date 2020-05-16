---
title: Test etme ve hata ayıklama
description: Birim testlerini, olguları ve onayları ve döküm işlevlerini kullanarak hisse programlarını test etme ve hata ayıklama hakkında bilgi edinin.
author: tcNickolas
ms.author: mamykhai@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.guide.testingdebugging
ms.openlocfilehash: 374ac42255ab6b2c5eff8ab7879b3a5103181f7f
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430926"
---
# <a name="testing-and-debugging"></a>Test etme ve hata ayıklama

Klasik programlamada olduğu gibi, hisse anlık programlarının amaçlanan gibi davranmasına ve yanlış bir hisse veya hatalı bir program tanılamasına olanak tanımak önemlidir.
Bu bölümde, test ve hata ayıklama için Q # tarafından sunulan araçlar ele alınmaktadır.

## <a name="unit-tests"></a>Birim testleri

Klasik programları test etmeye yönelik yaygın bir yaklaşım, bir kitaplıktaki kodu çalıştıran ve çıktısını beklenen bir çıktı ile karşılaştıran *birim testleri* adlı küçük programları yazmaktır.
Örneğin, `Square(2)` `4` $2 ^ 2 = $4 olan *bir priorı* öğrendiğimiz için, bunun döndürüldüğünden emin olmak isteyebilirsiniz.

S #, hisse programları için birim testleri oluşturmayı destekler ve bu, [xUnit](https://xunit.github.io/) birim test çerçevesi içinde testler olarak yürütülenebilir.

### <a name="creating-a-test-project"></a>Test projesi oluşturma

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Visual Studio 2019 ' i açın. `File`Menüye gidin ve öğesini seçin `New`  >  `Project...` .
Sağ üst köşede, için arama `Q#` yapın ve `Q# Test Project` şablonu seçin.

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

En sevdiğiniz komut satırınızdan aşağıdaki komutu çalıştırın:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Yeni projeniz tek bir dosyaya sahip olacak `Tests.qs` ve yeni Q # birim testlerini tanımlamak için uygun bir yer sağlar.
Başlangıçta bu dosya, `AllocateQubit` yeni ayrılmış bir qubitin $ \ket {0} $ durumunda olduğunu denetleyen ve bir ileti yazdıran bir örnek birim testi içeriyor:

```qsharp
    @Test("QuantumSimulator")
    operation AllocateQubit () : Unit {

        using (qubit = Qubit()) {
            Assert([PauliZ], [qubit], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

: New: any ve döndürülen bir bağımsız değişken alan tüm Q # işlemleri veya işlevleri `Unit` `Unit` , özniteliği aracılığıyla birim testi olarak işaretlenebilir `@Test("...")` . Üzerinde bu özniteliğin bağımsız değişkeni, `"QuantumSimulator"` testin yürütüldüğü hedefi belirtir. Birden çok hedef üzerinde tek bir test yürütülebilir. Örneğin, yukarıya bir öznitelik ekleyin `@Test("ResourcesEstimator")` `AllocateQubit` . 
```qsharp
    @Test("QuantumSimulator")
    @Test("ResourcesEstimator")
    operation AllocateQubit () : Unit {
        ...
```
Dosyayı kaydedin ve tüm testleri yürütün. Şimdi, AllocateQubit 'in miktar simülatör üzerinde yürütüldüğü ve ResourceEstimator 'da yürütüldüğü bir tane olmak üzere iki birim testi olmalıdır. 

Q # derleyicisi yerleşik hedefleri "niceleyici simülatörü", "Toffkaysimülatör" ve "ResourcesEstimator" değerini birim testleri için geçerli yürütme hedefleri olarak tanır. Özel bir yürütme hedefi tanımlamak için herhangi bir tam adı belirtmek de mümkündür. 

### <a name="running-q-unit-tests"></a>Q # birim testlerini çalıştırma

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Tek seferlik çözüm başına kurulum olarak `Test` menüsüne gidin ve öğesini seçin `Test Settings`  >  `Default Processor Architecture`  >  `X64` .

> [!TIP]
> Visual Studio için varsayılan işlemci mimarisi ayarı, `.suo` her çözüm için çözüm seçenekleri () dosyasında depolanır.
> Bu dosyayı silerseniz, `X64` İşlemci mimariniz olarak yeniden seçmeniz gerekir.

Projeyi derleyin, menüye gidin ve öğesini `Test` seçin `Windows`  >  `Test Explorer` . `AllocateQubit`, gruptaki testlerin listesinde görünür `Not Run Tests` . `Run All`Bu bireysel testi seçin veya çalıştırın, sonra geçmesi gerekir!

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

Testleri çalıştırmak için proje klasörüne (içeren klasör `Tests.csproj` ) gidin ve komutu yürütün:

```bash
$ dotnet restore
$ dotnet test
```

Aşağıdakine benzer bir çıktı almalısınız:

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

Birim testleri adına ve/veya yürütme hedefine göre filtrelenebilir:

```bash 
$ dotnet test --filter "Target=QuantumSimulator"
$ dotnet test --filter "Name=AllocateQubit"
```


***

İç işlevin <xref:microsoft.quantum.intrinsic.message> türü vardır `(String -> Unit)` ve tanılama iletilerinin oluşturulmasına izin vermez.

#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Test Gezgini 'nde bir testi yürütmeden ve teste tıkladığınızda, test yürütmesi hakkında bilgi içeren bir panel görüntülenir: başarılı/başarısız durum, geçen süre ve "çıktı" bağlantısı. "Çıkış" bağlantısına tıklarsanız, test çıktısı yeni bir pencerede açılır.

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

Her test için başarılı/başarısız durumu konsola tarafından yazdırılır `dotnet test` .
Başarısız testler için çıktılar, hatanın tanılanmasına yardımcı olmak üzere konsola da yazdırılır.

***

## <a name="facts-and-assertions"></a>Olgular ve Onaylamalar

Q # içindeki işlevlerin _mantıksal_ yan etkileri olmadığından, çıkış türü boş olan bir işlev yürütmenin _diğer_ etkileri hiçbir `()` zaman bir Q # programı içinden gözlemlenemez.
Diğer bir deyişle, bir hedef makine, `()` Bu atlama 'nin aşağıdaki Q # kodunun davranışını değiştirmeyeceği garantisi ile döndürülen hiçbir işlevi yürütmemelidir.
Bu `()` , işlevleri (ör. `Unit` ), soru-cevap ve hata ayıklama mantığını Q # programlarına ekleme yararlı bir araç haline getirir. 

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

Burada anahtar sözcüğü, `fail` hesaplamanın devam etmesi gerektiğini belirtir ve Q # programını çalıştıran hedef makinede bir özel durum ortaya koyar.
Tanım olarak, bu tür bir hata, bir deyime ulaşıldığında daha fazla Q # kodu çalıştırılıncaya kadar, Q # içinden gözlemlenemez `fail` .
Bu nedenle, çağrısına bir çağrı geçmemiz durumunda `PositivityFact` girişinin pozitif olması nedeniyle emin olabilir.

`PositivityFact`Ad alanından işlevini kullanarak aynı davranışı uygulayabileceğinizi unutmayın [`Fact`](xref:microsoft.quantum.diagnostics.fact) <xref:microsoft.quantum.diagnostics> :

```qsharp
    Fact(value <= 0, "Expected a positive number.");
```

Diğer yandan *onaylar,* olgulara benzer şekilde kullanılır, ancak hedef makinenin durumuna bağlı olabilir. Bunlar işlem olarak tanımlandıklarında, olgular işlev olarak tanımlanır (yukarıdaki gibi).
Ayrımı anlamak için, bir onaylama içinde aşağıdaki olgunun kullanımını göz önünde bulundurun:

```qsharp
operation AssertQubitsAreAvailable() : Unit
{
     Fact(GetQubitsAvailableToUse() > 0, "No qubits were actually available");
}
```

Burada, <xref:microsoft.quantum.environment.getqubitsavailabletouse> kullanılabilecek qubits sayısını döndürmek için işlemini kullanıyoruz.
Bu açıkça programın ve yürütme ortamının genel durumuna bağlı olduğundan, tanımımız da `AssertQubitsAreAvailable` bir işlem olmalıdır.
Ancak, işleve giriş olarak basit bir değer sağlamak için bu genel durumu kullanabiliriz `Bool` `Fact` .

Bu fikirlere yönelik olarak, [Prelude](xref:microsoft.quantum.libraries.standard.prelude) iki özellikle yararlı onaylama <xref:microsoft.quantum.intrinsic.assert> ve <xref:microsoft.quantum.intrinsic.assertprob> her ikisi de olarak modellenen işlemleri sunmaktadır `()` . Bu onayların her biri, belirli bir ölçümü, ölçümün gerçekleştirileceği bir hisse izini ve kuramsal bir sonucu açıklayan bir Pauli işleci alır.
Simülasyonu tarafından çalışan hedef makinelerde, [hiçbir kopyalama işlemi yapılmaz](https://en.wikipedia.org/wiki/No-cloning_theorem)ve bu tür ölçümlere, bu tür onayları geçen kaydı etkilemeden bu ölçümleri gerçekleştirebilir.
Daha sonra bir simülatör, yukarıdaki işleve benzer şekilde, `PositivityFact` kuramsal sonuç uygulamada gözlemlenmese hesaplamayı iptal edebilir:

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

Fiziksel hisse donanımı ' nde, hiçbir kopya olmaması durumunda hisse durumunun incelenmesi önlenir `Assert` ve `AssertProb` işlemler yalnızca `()` başka bir etkisi olmadan döndürülür.

<xref:microsoft.quantum.diagnostics>Ad alanı, `Assert` ailenin daha gelişmiş koşulları denetmamıza olanak sağlayan birkaç daha fazla işlev sunar. 

## <a name="dump-functions"></a>Döküm Işlevleri

Ad alanı, hisse programlarının sorunlarını gidermeye yardımcı olmak için, <xref:microsoft.quantum.diagnostics> hedef makinenin geçerli durumu ile bir dosyanın dökümünü yapan iki işlev sunar: <xref:microsoft.quantum.diagnostics.dumpmachine> ve <xref:microsoft.quantum.diagnostics.dumpregister> . Her birinin üretilen çıktısı, hedef makineye bağlıdır.

### <a name="dumpmachine"></a>DumpMachine

Hisse geliştirme seti 'nin bir parçası olarak dağıtılan tam eyalet hisse simülatörü, tüm hisse sisteminin [Wave işlevini](https://en.wikipedia.org/wiki/Wave_function) dosyaya yazar. tek boyutlu karmaşık sayıların dizisi olarak her bir öğenin hesaplama tabanlı durumu $ \ket{n} $ ölçü olasılığını temsil eden, $ \ket{n} = \ket{B_ {n-1}... BITS $ b_i $ için b_1b_0} $ \{ \} . Örneğin, yalnızca iki qubit ayrılmış bir makinede ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac {1} {\sqrt {2} } {00} \tus-\frac{(1 + ı)} {2} {10} \tus, \end{hizalaması} $ $ çağıran <xref:microsoft.quantum.diagnostics.dumpmachine> Bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.
Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{n} $ ölçgenin olasılığını anlatmaktadır. İlk satır için ayrıntılı:

* **`∣0❭:`** Bu satır `0` Hesaplama esası durumuna karşılık gelir
* **`0.707107 +  0.000000 i`**: Kartezyen biçiminde olasılık genliği.
* **` == `**: `equal` işaret, her iki eşdeğer temsili de ayırır.
* **`**********  `**: Büyüklük grafik gösterimi, sayısı `*` Bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı.
* **`[ 0.500000 ]`**: büyüklük sayısal değeri
* **`    ---`**: Genin aşamasının grafik gösterimi (aşağıya bakın).
* **`[ 0.0000 rad ]`**: aşamanın sayısal değeri (radyan cinsinden).

Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir. Büyüklük temsili düz bir şekilde görünür: bir çubuğunu gösterir, çubuğun ne kadar büyük olacağını daha `*` büyük hale gelir. Aşama için, aralıklara göre açıyı temsil etmek üzere aşağıdaki sembolleri göstereceğiz:

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

Aşağıdaki örneklerde `DumpMachine` bazı yaygın durumlar gösterilmektedir:

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
  > Bir qubit kimliği çalışma zamanında atanır ve qubitin ayrıldığı sıra veya bir qubit yazmaç içindeki konumu ile hizalı değildir.


#### <a name="visual-studio-2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Kodunuzda bir kesme noktası yerleştirerek ve bir qubit değişkeninin değerini inceleyerek, Visual Studio 'da bir qubit kimliği belirleyebilirsiniz, örneğin:
  > 
  > ![Visual Studio 'da qubit kimliği göster](~/media/qubit_id.png)
  >
  > dizininde bulunan qubit, `0` `register2` ID = `3` , index ile qubit ise `1` ID = `2` .

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > İşlevi kullanarak bir qubit kimliği düzenleyebilir <xref:microsoft.quantum.intrinsic.message> ve qubit değişkenini iletiye geçirerek, örneğin:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > Bu çıktıyı üreten:
  >```
  > 0=q:3; 1=q:2
  >```
  > Yani, dizinindeki qubit, `0` `register2` ID = `3` , index ile qubit 'in `1` ID = `2` olduğu anlamına gelir.


***

<xref:microsoft.quantum.diagnostics.dumpmachine>, <xref:microsoft.quantum.diagnostics> ad alanının bir parçası olduğundan, bunu kullanabilmek için bir ifade eklemeniz gerekir `open` :

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

<xref:microsoft.quantum.diagnostics.dumpregister>benzer şekilde çalışarak <xref:microsoft.quantum.diagnostics.dumpmachine> , yalnızca ilgili qubits ile ilgili bilgi miktarını sınırlamak için bir qubit dizisi de alır.

İle olduğu gibi <xref:microsoft.quantum.diagnostics.dumpmachine> , tarafından oluşturulan bilgiler <xref:microsoft.quantum.diagnostics.dumpregister> hedef makineye göre değişir. Tam eyalet hisse simülatörü için, Wave işlevine, ile aynı biçimde belirtilen qubits tarafından oluşturulan küresel bir aşamaya kadar yazar <xref:microsoft.quantum.diagnostics.dumpmachine> .  Örneğin, yalnızca iki qubit ayrılmış bir makineye ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac {1} {\sqrt {2} } {00} \tus-\frac{(1 + ı)} {2} {10} \tus=-e ^ {-i \ Pi/4} ((\frac {1} {\sqrt {2} } {0} \tus-\frac{(1 + i)} {2} \ket {1} ) \otimes \frac{-(1 + ı)} {\sqrt {2} } {0} \tus), \end{hizalaması} $ $ çağrısı <xref:microsoft.quantum.diagnostics.dumpregister> `qubit[0]` Bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

ve <xref:microsoft.quantum.diagnostics.dumpregister> için çağrı `qubit[1]` Bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Genel olarak, başka bir yazmaç ile ayrılmış bir kaydın durumu saf bir durum değil, karışık bir durumdur. Bu durumda, <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi verir:

```
Qubits provided (0;) are entangled with some other qubit.
```

Aşağıdaki örnekte, her ikisini de <xref:microsoft.quantum.diagnostics.dumpregister> ve <xref:microsoft.quantum.diagnostics.dumpmachine> Q # kodunuzda nasıl kullanabileceğiniz gösterilmektedir:

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

`Assert` `Dump` , Ve işlevleri ve işlemleri üzerinde, Q # standart Visual Studio hata ayıklama özellikleri alt kümesini destekler: [satır kesme noktaları ayarlama](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [F10 kullanarak kod üzerinden atlama](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) ve [Klasik değişkenlerin değerlerini inceleme](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows) işlemi, benzeticide kod yürütme sırasında mümkün değildir.

Visual Studio Code hata ayıklaması, C# tarafından desteklenen ve OmniSharp tarafından desteklenen Visual Studio Code uzantısı Için sağlanan hata ayıklama yeteneklerini kullanır ve [en son sürümü](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)yüklemeyi gerektirir. 
