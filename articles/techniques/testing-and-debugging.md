---
title: 'S # teknikleri-test ve hata ayıklama | Microsoft Docs'
description: 'S # teknikleri-test ve hata ayıklama'
author: tcNickolas
ms.author: mamykhai@microsoft.com
uid: microsoft.quantum.techniques.testing-and-debugging
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 25679331f1bed9f98b86c6eb20f511c891bac1af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183497"
---
# <a name="testing-and-debugging"></a>Test ve hata ayıklama

Klasik programlamada olduğu gibi, hisse anlık programlarının amaçlanan gibi davranmasına ve yanlış bir hisse veya hatalı bir program tanılamasına olanak tanımak önemlidir.
Bu bölümde, test ve hata ayıklama için Q # tarafından sunulan araçlar ele alınmaktadır.

## <a name="unit-tests"></a>Birim testleri

Klasik programları test etmeye yönelik yaygın bir yaklaşım, bir kitaplıktaki kodu çalıştıran ve çıktısını beklenen bir çıktı ile karşılaştıran *birim testleri* adlı küçük programları yazmaktır.
Örneğin, $2 ^ 2 = $4 olan *bir priorı* öğrendiğimiz için `Square(2)` `4`döndürdüğünden emin olmak istiyoruz.

S #, hisse programları için birim testleri oluşturmayı destekler ve bu, [xUnit](https://xunit.github.io/) birim test çerçevesi içinde testler olarak yürütülenebilir.

### <a name="creating-a-test-project"></a>Test projesi oluşturma

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Visual Studio 2019 ' i açın. `File` menüsüne gidin ve `New` > `Project...`' yı seçin.
Proje şablonu Gezgini ' nde, `Installed` > `Visual C#`altında `Q# Test Project` şablonunu seçin.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Komut satırı/Visual Studio Code](#tab/tabid-vscode)

En sevdiğiniz komut satırınızdan aşağıdaki komutu çalıştırın:
```bash
$ dotnet new xunit -lang Q# -o Tests
$ cd Tests
$ code . # To open in Visual Studio Code
```

****

Her iki durumda da, yeni projenizin açık iki dosyası olur.
İlk dosya `Tests.qs`, yeni Q # birim testlerini tanımlamak için uygun bir yer sağlar.
Başlangıçta bu dosya, yeni ayrılmış bir qubitin $ \ket{0}$ durumunda olduğunu denetleyen ve bir ileti yazdıran bir örnek birim testi `AllocateQubitTest` içerir:

```qsharp
    operation AllocateQubitTest () : Unit {
        using (q = Qubit()) {
            Assert([PauliZ], [q], Zero, "Newly allocated qubit must be in the |0⟩ state.");
        }
        
        Message("Test passed");
    }
```

`(Unit -> Unit)` ile uyumlu tür `(Unit => Unit)` veya işlev ile uyumlu herhangi bir Q # işlemi, birim testi olarak yürütülebilir. 

İkinci dosya `TestSuiteRunner.cs`, Q # birim testlerini bulan ve çalıştıran bir yöntemi içerir. Bu yöntem, `OperationDriver` özniteliğiyle açıklama eklenmiş `TestTarget`.
`OperationDriver` özniteliği, Microsoft. hisse. simülasyon. xUnit uzantı kitaplığı uzantısının bir parçasıdır.
Birim test çerçevesi, bulduğu her Q # birim testi için `TestTarget` yöntemini çağırır.
Framework, birim testi açıklamasını `op` bağımsız değişkeni aracılığıyla yöntemine geçirir. Aşağıdaki kod satırı:
```csharp
op.TestOperationRunner(sim);
```
`QuantumSimulator`birim testini yürütür.

Varsayılan olarak, birim testi bulma mekanizması, aşağıdaki özellikleri karşılayan tüm Q # işlevlerine veya uyumlu türde işlemlere bakar:
* `OperationDriver` özniteliğiyle açıklama eklenmiş yöntemle aynı derlemede bulunur.
* `OperationDriver` özniteliğiyle açıklama eklenmiş yöntemle aynı ad alanında bulunur.
* `Test`ile biten bir ada sahiptir.

Bir derleme, bir ad alanı ve birim testi işlevleri ve işlemleri için bir sonek, `OperationDriver` özniteliğinin isteğe bağlı parametreleri kullanılarak ayarlanabilir:
* `AssemblyName` parametresi, testler için aranmakta olan derlemenin adını ayarlar.
* `TestNamespace` parametresi, testler için aranmakta olan ad alanının adını ayarlar.
* `Suffix`, birim testleri olarak kabul edilen işlem veya işlev adlarının sonekini ayarlar.

Ayrıca, isteğe bağlı `TestCasePrefix` parametresi, test çalışmasının adı için bir ön ek ayarlamanıza olanak sağlar. İşlem adının önündeki önek, test çalışmaları listesinde görünür. Örneğin, `TestCasePrefix = "QSim:"`, `AllocateQubitTest` bulunan testlerin listesinde `QSim:AllocateQubitTest` olarak görünmesine neden olur. Bu, örneğin bir testi çalıştırmak için hangi benzeticinin kullanıldığını göstermek için yararlı olabilir.

### <a name="running-q-unit-tests"></a>Q # birim testlerini çalıştırma

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Tek seferlik çözüm başına kurulum olarak `Test` menüsüne gidin ve `Test Settings` > `Default Processor Architecture` > `X64`' nı seçin.

> [!TIP]
> Visual Studio için varsayılan işlemci mimarisi ayarı, her çözüm için çözüm seçenekleri (`.suo`) dosyasında depolanır.
> Bu dosyayı silerseniz, İşlemci mimariniz olarak `X64` yeniden seçmeniz gerekecektir.

Projeyi derleyin, `Test` menüsüne gidin ve `Windows` > `Test Explorer`' yı seçin. `AllocateQubitTest`, `Not Run Tests` grubundaki testlerin listesinde görünür. `Run All` seçin veya bu testi çalıştırın ve başarılı olur!

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Komut satırı/Visual Studio Code](#tab/tabid-vscode)

Testleri çalıştırmak için proje klasörüne (`Tests.csproj`içeren klasör) gidin ve komutu yürütün:

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

***

## <a name="logging-and-assertions"></a>Günlüğe kaydetme ve onaylama

Q # içindeki işlevlerin önemli bir sonucu, çıkış türü boş olan bir işlevi yürütmenin herhangi bir etkisi `()`, hiçbir zaman bir Q # programı içinden gözlemlenemez.
Diğer bir deyişle, bir hedef makine, bu atlama 'nin aşağıdaki Q # kodunun davranışını değiştirmeyeceği garantisi ile `()` döndüren herhangi bir işlevi yürütmemelidir.
Bu işlem, soru-cevap ve hata ayıklama mantığını Q # programlarına eklemek için kullanışlı bir araç `()` döndüren işlevleri yapar. 

### <a name="logging"></a>Günlüğe kaydetme

<xref:microsoft.quantum.intrinsic.message> iç işlev `(String -> Unit)` türüne sahiptir ve tanılama iletilerinin oluşturulmasına izin vermez.

`QuantumSimulator` `onLog` eylemi, Q # kodu `Message`çağırdığında gerçekleştirilen eylemleri tanımlamak için kullanılabilir. Varsayılan olarak günlüğe kaydedilen iletiler standart çıktıya yazdırılır.

Bir birim testi paketi tanımlarken, günlüğe kaydedilen iletiler test çıktısına yönlendirilebilir. Bir proje, Q # test projesi şablonundan oluşturulduğunda, bu yeniden yönlendirme, paket için önceden yapılandırılmıştır ve varsayılan olarak aşağıdaki gibi oluşturulur:

```qsharp
using (var sim = new QuantumSimulator())
{
    // OnLog defines action(s) performed when Q# test calls operation Message
    sim.OnLog += (msg) => { output.WriteLine(msg); };
    op.TestOperationRunner(sim);
}
```

#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

Test Gezgini 'nde bir testi yürütmeden ve teste tıkladığınızda, test yürütmesi hakkında bilgi içeren bir panel görüntülenir: başarılı/başarısız durum, geçen süre ve "çıktı" bağlantısı. "Çıkış" bağlantısına tıklarsanız, test çıktısı yeni bir pencerede açılır.

![test çıktısı](~/media/unit-test-output.png)

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Komut satırı/Visual Studio Code](#tab/tabid-vscode)

Her bir testin geçiş/başarısızlık durumu konsola `dotnet test`göre yazdırılır.
Başarısız testler için, yukarıdaki `output.WriteLine(msg)` çağrısının sonucu olarak günlüğe kaydedilen çıktılar da hatanın tanılanmasına yardımcı olmak için konsola yazdırılır.

***

### <a name="assertions"></a>Onaylama

Onayları uygulamak için aynı Logic de uygulanabilir. Basit bir örnek ele alalım:

```qsharp
function AssertPositive(value : Double) : Unit 
{
    if (value <= 0) 
    {
        fail "Expected a positive number.";
    }
}
```

Burada, anahtar sözcüğü `fail` hesaplamanın devam etmesi gerektiğini belirtir ve Q # programını çalıştıran hedef makinede bir özel durum ortaya koyar.
Tanım olarak, bu tür bir hata, `fail` deyiminden sonra başka bir Q # kodu çalıştırılıncaya kadar, Q # içinden gözlemlenemez.
Bu nedenle, `AssertPositive`bir çağrıyı aşdığımızda, girişi pozitif olduğundan emin olabilir.

Bu fikirlere yönelik olarak, [Prelude](xref:microsoft.quantum.libraries.standard.prelude) , <xref:microsoft.quantum.intrinsic.assert> ve <xref:microsoft.quantum.intrinsic.assertprob> her ikisi de `()`üzerinde işlem olarak modellenen iki daha kullanışlı onaylama sağlar. Bu onayların her biri, belirli bir ölçümü, ölçümün gerçekleştirileceği bir hisse izini ve kuramsal bir sonucu açıklayan bir Pauli işleci alır.
Simülasyonu tarafından çalışan hedef makinelerde, [hiçbir kopyalama işlemi yapılmaz](https://en.wikipedia.org/wiki/No-cloning_theorem)ve bu tür ölçümlere, bu tür onayları geçen kaydı etkilemeden bu ölçümleri gerçekleştirebilir.
Daha sonra bir simülatör, yukarıdaki `AssertPositive` işleve benzer şekilde, kuramsal sonuç uygulamada gözlemlenmese hesaplamayı iptal edebilir:

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

Kopya olmaması gereken fiziksel hisse donanımı, `Assert` ve `AssertProb` işlemleri yalnızca başka bir efekt olmadan `()` geri dönmeyecektir.

<xref:microsoft.quantum.diagnostics> ad alanı, daha gelişmiş koşulları denetmamıza izin veren `Assert` aile işlevlerinin daha birçok işlevini sağlar. 

## <a name="dump-functions"></a>Döküm Işlevleri

<xref:microsoft.quantum.diagnostics> ad alanı, hisse programları sorunlarını gidermeye yardımcı olmak için, hedef makinenin geçerli durumu bir dosyaya döküm veren iki işlev sunar: <xref:microsoft.quantum.diagnostics.dumpmachine> ve <xref:microsoft.quantum.diagnostics.dumpregister>. Her birinin üretilen çıktısı, hedef makineye bağlıdır.

### <a name="dumpmachine"></a>DumpMachine

Hisse geliştirme seti 'nin bir parçası olarak dağıtılan tam eyalet hisse Benzetici, her bir öğe için her öğenin genliğini temsil eden tek boyutlu karmaşık sayıların [Wave işlevine](https://en.wikipedia.org/wiki/Wave_function) dosya içine yazar. hesaplama temelini ölçme olasılığı $ \ket{n} $, burada $ \ket{n} = \ket{B_{n-1}... BITS $\{b_i\}$ için b_1b_0} $. Örneğin, yalnızca iki qubit ayrılmış bir makinede ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac{1}{\sqrt{2}} \ment{00}-\frac{(1 + ı)}{2} \tus{10}, \end{hizalaması} $ $ çağıran <xref:microsoft.quantum.diagnostics.dumpmachine> bu çıktıyı oluşturur :

```
# wave function for qubits with ids (least to most significant): 0;1
∣0❭:     0.707107 +  0.000000 i  ==     **********           [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
∣2❭:    -0.500000 + -0.500000 i  ==     **********           [ 0.500000 ]   /     [ -2.35619 rad ]
∣3❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.
Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{n} $ ölçgenin olasılığını anlatmaktadır. İlk satır için ayrıntılı:

* Bu satır **`∣0❭:`** `0` hesaplama esası durumuna karşılık gelir
* **`0.707107 +  0.000000 i`** : Kartezyen biçimdeki olasılık genliği.
* **` == `** : `equal` işareti her iki denk gösterimi ayırır.
* **`**********  `** : büyüklük grafik gösterimi, `*` sayısı bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı.
* **`[ 0.500000 ]`** : büyüklük sayısal değeri
* **`    ---`** : genin aşamasının grafik gösterimi (aşağıya bakın).
* **`[ 0.0000 rad ]`** : aşamanın sayısal değeri (radyan cinsinden).

Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir. Büyüklük temsili düz bir işlemdir: `*`bir çubuk gösterir, çubuğun ne kadar büyük olduğu büyük olasılıkla daha büyük olur. Aşama için, aralıklara göre açıyı temsil etmek üzere aşağıdaki sembolleri göstereceğiz:

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

Aşağıdaki örneklerde bazı yaygın durumlar için `DumpMachine` gösterilmektedir:

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


#### <a name="visual-studio-2019tabtabid-vs2019"></a>[Visual Studio 2019](#tab/tabid-vs2019)

  > [!TIP]
  > Kodunuzda bir kesme noktası yerleştirerek ve bir qubit değişkeninin değerini inceleyerek, Visual Studio 'da bir qubit kimliği belirleyebilirsiniz, örneğin:
  > 
  > ![Visual Studio 'da qubit kimliği göster](~/media/qubit_id.png)
  >
  > `register2` üzerindeki Dizin `0` olan qubit, ID =`3`, Index `1` ile qubit, ID =`2`içerir.

#### <a name="command-line--visual-studio-codetabtabid-vscode"></a>[Komut satırı/Visual Studio Code](#tab/tabid-vscode)

  > [!TIP]
  > <xref:microsoft.quantum.intrinsic.message> işlevini kullanarak bir qubit Kimliği belirleyebilir ve qubit değişkenini iletiye geçirerek, örneğin:
  >
  > ```qsharp
  > Message($"0={register2[0]}; 1={register2[1]}");
  > ```
  > 
  > Bu çıktıyı üreten:
  >```
  > 0=q:3; 1=q:2
  >```
  > Yani, Dizin `0` `register2` üzerindeki qubit 'in ID =`3`olduğu, Index `1` ile qubit 'in ID =`2`olduğu anlamına gelir.


***

<xref:microsoft.quantum.diagnostics.dumpmachine>, <xref:microsoft.quantum.diagnostics> ad alanının bir parçası olduğundan, bunu kullanabilmeniz için bir `open` ifadesini eklemeniz gerekir:

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

<xref:microsoft.quantum.diagnostics.dumpregister>, <xref:microsoft.quantum.diagnostics.dumpmachine>gibi çalışarak, yalnızca ilgili qubits ile ilgili bilgi miktarını sınırlamak için de bir qubit dizisi alır.

<xref:microsoft.quantum.diagnostics.dumpmachine>olduğu gibi, <xref:microsoft.quantum.diagnostics.dumpregister> tarafından oluşturulan bilgiler hedef makineye göre değişir. Tam eyalet hisse simülatörü için, Wave işlevi, <xref:microsoft.quantum.diagnostics.dumpmachine>ile aynı biçimde oluşturulan qubits tarafından oluşturulan küresel bir aşamaya kadar dosya içine yazar.  Örneğin, yalnızca iki qubit ayrılmış bir makineye ve hisse durumu $ $ \begin{hizalaması} \ket{\psı} = \frac{1}{\sqrt{2}} \tus' e sahip bir makine alın{00}-\frac{(1 + i)}{2} \ayraç{10} =-e ^ {-i \ Pi/4} ((\frac{1}{\sqrt{2}} \ demet{0}-\frac{(1 + i)}{2} \ket{1}) \otimes \frac{-(1 + ı)} {\sqrt{2}} \tus{0}), \end{hizalaması} $ $ <xref:microsoft.quantum.diagnostics.dumpregister> için çağıran `qubit[0]` bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 0
∣0❭:    -0.707107 + -0.707107 i  ==     ******************** [ 1.000000 ]  /      [ -2.35619 rad ]
∣1❭:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
```

ve `qubit[1]` için <xref:microsoft.quantum.diagnostics.dumpregister> çağrısı bu çıktıyı oluşturur:

```
# wave function for qubits with ids (least to most significant): 1
∣0❭:     0.707107 +  0.000000 i  ==     ***********          [ 0.500000 ]     --- [  0.00000 rad ]
∣1❭:    -0.500000 + -0.500000 i  ==     ***********          [ 0.500000 ]  /      [ -2.35619 rad ]
```

Genel olarak, başka bir yazmaç ile ayrılmış bir kaydın durumu saf bir durum değil, karışık bir durumdur. Bu durumda <xref:microsoft.quantum.diagnostics.dumpregister> aşağıdaki iletiyi verir:

```
Qubits provided (0;) are entangled with some other qubit.
```

Aşağıdaki örnek, Q # kodunuzda hem <xref:microsoft.quantum.diagnostics.dumpregister> hem de <xref:microsoft.quantum.diagnostics.dumpmachine> nasıl kullanabileceğinizi gösterir:

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

`Assert` ve `Dump` işlevlerinin ve işlemlerinin üstünde, Q #, standart Visual Studio hata ayıklama özellikleri alt kümesini destekler: [satır kesme noktaları ayarlama](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints), [F10 kullanarak kodu atlama](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger) ve [Klasik değişkenlerin değerlerini İnceleme ](https://docs.microsoft.com/visualstudio/debugger/autos-and-locals-windows)simülatör üzerinde kod yürütme sırasında hepsi mümkündür.

Visual Studio Code 'de hata ayıklama henüz desteklenmiyor.
