---
title: "Q 'de qubit düzeyi programları yazma ve benzetimini yapma #"
description: Bireysel qubit düzeyinde çalışan bir hisse programını yazma ve benzetimi yapma hakkında adım adım öğretici
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 10/06/2019
uid: microsoft.quantum.circuit-tutorial
ms.topic: tutorial
ms.openlocfilehash: 05d3292e1c6e3c8c1163c460f2aaa51c591aa1d5
ms.sourcegitcommit: 8d9d392bf5e114ae223e6f689ba80d25866ff586
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84422249"
---
# <a name="tutorial-write-and-simulate-qubit-level-programs-in-q"></a>Öğretici: Q 'da qubit düzeyi programları yazma ve benzetimini yapma\#

Her bir qubit üzerinde çalışan temel bir hisse dili programını yazma ve benzetimi yapma hakkında hisse geliştirme seti öğreticisine hoş geldiniz. 

Q #, büyük ölçekli hisse programları için öncelikli olarak yüksek düzeyde bir programlama dili olarak oluşturulsa da, daha düşük hisse bitlerinin düzeyini araştırmak için yalnızca kolayca kullanılabilir.
Q # ' ın esnekliği, kullanıcıların bu tür bir soyutlama düzeyinden elde etmesine izin verir ve bu öğreticide, qubits 'e daha fazla yaklaşıyoruz.
Özellikle de, birçok büyük hisse algoritmaya integral olan bir alt yordam olan [hisse](https://en.wikipedia.org/wiki/Quantum_Fourier_transform)

Hisse senedi bilgi işlemenin bu alt düzey görünümünün genellikle, bir sistemin belirli qugeler için sıralı uygulamayı temsil eden "[hisse devreleri](xref:microsoft.quantum.concepts.circuits)" bakımından açıklandığına bakın.

Bu nedenle, ardışık olarak uygulanan tek ve Multi-qubit işlemleri "devre diyagramı" içinde kolayca temsil edilebilir.
Bu durumda, aşağıdaki gösterimi bir devre olarak bulunan tam üç qubit hisse Fourier dönüşümünü gerçekleştirmek için bir Q # işlemi tanımlayacağız:

<br/>
<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

## <a name="prerequisites"></a>Ön koşullar

* [Install](xref:microsoft.quantum.install) Tercih ettiğiniz dil ve geliştirme ortamınızı kullanarak hisse geliştirme setini kullanın.
* Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun


## <a name="in-this-tutorial-youll-learn-how-to"></a>Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:

> [!div class="checklist"]
> * Q 'da hisse işlemleri tanımlama #
> * Doğrudan komut satırından veya klasik ana bilgisayar programını kullanarak Q # işlemlerini doğrudan çağırın
> * Ölçüm çıkışına qubit ayırmayı bir hisse alma işlemi benzetimi yap
> * Hisse sisteminin sanal dalga işlevinin işlem boyunca nasıl gelişdiğini gözlemleyin

Microsoft 'un hisse geliştirme seti ile bir hisse programın çalıştırılması genellikle iki bölümden oluşur:
1. Bu programın kendisi, Q # hisse programlama dili kullanılarak uygulanır ve ardından bir hisse bilgisayar veya hisse Benzetici üzerinde çalışmak üzere çağırılır. Bunlardan oluşur 
    - S # işlemleri: hisse kayıtları ile çalışan alt yordamlar ve 
    - S # işlevleri: hisse algoritması içinde kullanılan klasik alt yordamlar.
2. Hisse programını çağırmak ve üzerinde çalıştırılması gereken hedef makineyi belirtmek için kullanılan giriş noktası.
    Bu işlem doğrudan komut satırından veya Python veya C# gibi bir klasik programlama dilinde yazılmış bir konak programı aracılığıyla yapılabilir.
    Bu öğretici, tercih ettiğiniz yönteme ilişkin yönergeleri içerir.

## <a name="allocate-qubits-and-define-quantum-operations"></a>Qubits ayırın ve hisse alma işlemlerini tanımlayın

Bu öğreticinin ilk bölümünde `Perform3qubitQFT` , üç qubit üzerinde hisse Fourier dönüşümünü gerçekleştiren Q # işleminin tanımlanması oluşur. 

Ayrıca, [`DumpMachine`](xref:microsoft.quantum.diagnostics.dumpmachine) üç qubit sistemimizin benzetilen dalga işlevinin işlem genelinde geliştikçe, işlevini kullanacağız.

İlk adım, Q # projenizi ve dosyanızı oluşturmaktır.
Bunun adımları programı çağırmak için kullanacağınız ortama bağlıdır ve ilgili [yükleme kılavuzlarındaki](xref:microsoft.quantum.install)ayrıntıları bulabilirsiniz.

Adım adım, dosyanın bileşenlerinde size kılavuzluk ederiz, ancak kod aşağıdaki tam bir blok olarak da kullanılabilir.

### <a name="namespaces-to-access-other-q-operations"></a>Diğer Q # işlemlerine erişmek için ad alanları
Dosya içinde, önce derleyici tarafından erişilecek ad alanını tanımlayacağız `NamespaceQFT` .
Var olan Q # işlemlerini kullanmaya yönelik işlemimiz için ilgili `Microsoft.Quantum.<>` ad alanlarını açarız.

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    // operations go here
}
```

### <a name="define-operations-with-arguments-and-returns"></a>Bağımsız değişkenlerle işlemleri tanımlama ve geri dönüş
Sonra, işlemi tanımladık `Perform3qubitQFT` :

```qsharp
    operation Perform3qubitQFT() : Unit {
        // do stuff
    }
```

Şimdilik işlem herhangi bir bağımsız değişken almaz ve bu durumda---hiçbir şey döndürmez; bu durumda, `Unit` `void` Python 'Da C# veya boş bir tanımlama alanı olan bir nesneyi döndüren bir nesne döndürür `Tuple[()]` .
Daha sonra, bunu bir dizi ölçüm sonucu döndürecek şekilde değiştirecek ve bu noktada `Unit` Değiştirilecek `Result[]` . 

### <a name="allocate-qubits-with-using"></a>İle qubit ayırın`using`
Q # operasyonumuza göre, ilk olarak deyimle üç qubit kaydı ayırdık `using` :

```qsharp
        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

        }
```

İle `using` , qubits $ \ket $ durumunda otomatik olarak ayrılır {0} . Bunu [`Message(<string>)`](xref:microsoft.quantum.intrinsic.message) [`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine) , ve ' ı kullanarak, bir dizeyi ve sistemin geçerli durumunu konsola yazdıracak şekilde doğrulayabiliriz.

> [!NOTE]
> `Message(<string>)`Ve `DumpMachine()` işlevleri ( [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ve [`Microsoft.Quantum.Diagnostics`](xref:microsoft.quantum.diagnostics) sırasıyla), her ikisi de doğrudan konsola yazdırılır. Gerçek bir hisse hesaplamasında olduğu gibi, Q #, qubit durumlarına doğrudan erişememize izin vermez.
> Ancak, `DumpMachine` hedef makinenin geçerli durumunu yazdırdığından, tam durum simülatörü ile birlikte kullanıldığında hata ayıklama ve öğrenimi için değerli öngörüler sağlayabilir.


### <a name="applying-single-qubit-and-controlled-gates"></a>Tek qubit ve denetimli kapıları uygulama

Daha sonra, işlemin kendisini oluşturan kapıları uyguladık.
S #, ad alanında işlem olarak birçok temel hisse kapısı içeriyor [`Microsoft.Quantum.Intrinsic`](xref:microsoft.quantum.intrinsic) ve bunlar özel durum değildir. 

Bir Q # işlemi içinde, callables çağıran deyimler sıralı sırada yürütülür.
Bu nedenle, uygulanacak ilk kapı [`H`](xref:microsoft.quantum.intrinsic.h) ilk qubit 'e (Hadamard) sahiptir:

<br/>
<img src="./qft_firstH.PNG" alt="Circuit diagram for three qubit QFT through first Hadamard" width="120">

Bir kayıttaki belirli bir qubit 'e bir işlem uygulamak için (bir dizideki tek bir `Qubit` dizi `Qubit[]` ) standart dizin gösterimini kullanırız.
Bu nedenle, [`H`](xref:microsoft.quantum.intrinsic.h) kayıt yaptığımız ilk qubit 'e uygulamak şu `qs` biçimdedir:

```qsharp
            H(qs[0]);
```

`H`(Hadamard) geçidini tek bir qubits 'e uygulamanın yanı sıra, QFT devresi öncelikle denetlenen döndürmeler ' i içerir [`R1`](xref:microsoft.quantum.intrinsic.r1) .
`R1(θ, <qubit>)`Genel içindeki bir işlem {0} , qubit 'in $ \ket $ bileşenini $ \ket $ bileşenine bir $e dönüşü uygulanırken, aynı şekilde değişmeden bırakır {1} .

#### <a name="controlled-operations"></a>Denetlenen işlemler

Q # bir veya daha fazla denetim qubits üzerinde bir işlemin yürütülmesini çok kolay hale getirir.
Genel olarak, yalnızca ile çağrıyı önliyoruz `Controlled` ve işlem bağımsız değişkenleri şu şekilde değişir:

 `Op(<normal args>)`$ \-$ `Controlled Op([<control qubits>], (<normal args>))` .

Tek bir qubit olsa bile denetim qubits 'in bir dizi olarak sağlanması gerektiğini unutmayın.

Sonrasında, `H` sonraki kapıların `R1` ilk qubit üzerinde hareket eden kapıları olduğunu ve ikinci/üçüncü tarafından denetlendiğini görüyoruz:

<br/>
<img src="./qft_firstqubit.PNG" alt="Circuit diagram for three qubit QFT through first qubit" width="310">

Bunları şu şekilde çağırır

```qsharp
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));
```

Bu [`PI()`](xref:microsoft.quantum.math.pi) işlevi, [`Microsoft.Quantum.Math`](xref:microsoft.quantum.math) ad alanından Pi radyana kadar olan işlevleri tanımlamak için kullandığımızda aklınızda olduğunu unutmayın.
Ayrıca, bir `Double` (örn.), bir `2.0` tamsayı ile bölmek bir `2` tür hatası oluşturacak. 

> [!TIP]
> `R1(π/2)`ve `R1(π/4)` , `S` ve `T` işlemlerine eşdeğerdir (Ayrıca içinde `Microsoft.Quantum.Intrinsic` ).


`H`İkinci ve üçüncü qubits 'e ilgili işlemler ve denetlenen döndürmeler uygulandıktan sonra:

```qsharp
            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);
```

[`SWAP`](xref:microsoft.quantum.intrinsic.swap)devresini tamamlamaya yönelik yalnızca bir geçit uygulamanız gerekir:

```qsharp
            SWAP(qs[2], qs[0]);
```

Bu gereklidir çünkü, bu işlem, bu, boyut ve alt yordamın daha büyük algoritmalara sorunsuz bir şekilde tümleştirilmesini sağlar.

Bu nedenle, hisse uygun bir şekilde, hımız dönüştürme işlemi için, Q # işlemimize bir HBIT düzeyi işlem yazma

<img src="./qft_full.PNG" alt="Three qubit quantum Fourier transform circuit diagram" width="600">

Ancak henüz bir gün arayamıyoruz.
Qubits 'lerimiz {0} , ayrıldığımızda $ \ket $ durumunda ve çok daha fazla olduğu gibi, her ne kadar iyi olduğu gibi, her şeyi bulduğumuz gibi bırakmamız gerekir (veya daha iyi!).

### <a name="deallocate-qubits"></a>Qubit serbest bırakma

[`DumpMachine()`](xref:microsoft.quantum.diagnostics.dumpmachine)İşlem sonrası durumunu görmek için yeniden çağrımız ve son olarak, [`ResetAll`](xref:microsoft.quantum.intrinsic.resetall) işlemi tamamlamadan önce qubits 'i $ \ket $ ile sıfırlamak için qubit kayıt için geçerlidir {0} :

```qsharp
            Message("After:");
            DumpMachine();

            ResetAll(qs);
```

Tüm serbest bırakılmış qubits 'in {0} Bu aynı qubit 'leri (bir nadir kaynağı) kullanmaya başladıklarında, diğer işlemlerin durumlarını tam olarak bilmesini sağlamasına izin vermek için, bir Q # öğesinin temel bir özelliğidir.
Buna ek olarak, bu, sistemdeki diğer qubits ile zenginler olmasını sağlar.
Bir ayırma bloğunun sonunda sıfırlama gerçekleştirildiyse `using` , bir çalışma zamanı hatası oluşur.

Tam Q # dosyanız şu şekilde görünmelidir:

```qsharp
namespace NamespaceQFT {
    open Microsoft.Quantum.Intrinsic;
    open Microsoft.Quantum.Diagnostics;
    open Microsoft.Quantum.Math;
    open Microsoft.Quantum.Arrays;

    operation Perform3qubitQFT() : Unit {

        using (qs = Qubit[3]) {

            Message("Initial state |000>:");
            DumpMachine();

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("After:");
            DumpMachine();

            ResetAll(qs);
        }
    }
}
```


Q # dosyası ve işlem tamamlandıktan sonra, hisse mamızda program çağrılmaya ve benzetimine hazırlanmaktadır.

## <a name="execute-the-program"></a>Programı Yürüt

Q # işleminizi bir `.qs` dosyada tanımladık, şimdi bu işlemi çağırmalı ve döndürülen tüm klasik verileri gözlemleyeceğiz.
Şimdilik, döndürülen hiçbir şey yok (daha sonra işlem tarafından tanımlanan işlemin döndürdüğü geri çek `Unit` ), ancak daha sonra Q # işlemini bir ölçüm sonuçları dizisi () döndürecek şekilde değiştirdiğimiz zaman `Result[]` bunu ele alınacaktır.

Q # programı, bunu çağırmak için kullanılan ortamlara göre değişiklik yapalım olsa da, bunu yapmanın bir yolu farklılık gösterecektir. Bu nedenle, kuruluma karşılık gelen sekmedeki yönergeleri izlemeniz yeterlidir: Q # komut satırı uygulamasından çalışma veya Python ya da C# ' de bir konak programı kullanma.

#### <a name="command-line"></a>[Komut satırı](#tab/tabid-cmdline)

Q # programını komut satırından çalıştırmak, Q # dosyasında yalnızca küçük bir değişiklik yapılmasını gerektirir.

`@EntryPoint()`İşlem tanımından önceki bir satıra eklemeniz yeterlidir:

```qsharp
    @EntryPoint()
    operation Perform3qubitQFT() : Unit {
        // ...
```

Programı çalıştırmak için, terminali projenizin klasöründe açın ve şunu girin

```dotnetcli
dotnet run
```

Yürütmeden sonra, `Message` `DumpMachine` aşağıda ve aşağıdaki çıktıları konsolunuza görmeniz gerekir.


#### <a name="python"></a>[Python](#tab/tabid-python)

Python ana bilgisayar dosyası oluştur: `host.py` .

Ana bilgisayar dosyası şu şekilde oluşturulur: 
1. İlk olarak, `qsharp` Modül yükleyicisini Q # birlikte çalışabilirlik için kaydeden modülünü içeri aktardık. 
    Bu, q # çalışma alanlarına izin verir (örneğin, `NamespaceQFT` q # dosyası içinde tanımladık), ' den, q # işlemlerini içeri aktarabilmemiz Için Python modülleri olarak görünür.
2. Ardından, bu durumda---doğrudan çağıracağız olan Q # işlemlerini içeri aktarın `Perform3qubitQFT` .
    Giriş noktasını yalnızca bir Q # programına (ve gibi _değil_ `H` `R1` , diğer q # işlemleri tarafından çağrılan ancak hiçbir şekilde klasik ana bilgisayar tarafından çağırılan) içeri aktardık.
3. Q # işlemlerine veya işlevlerine benzetim yaparken, bu formu `<Q#callable>.simulate(<args>)` hedef makinede çalıştırmak için kullanın `QuantumSimulator()` . 

> [!NOTE]
> İşlemi farklı bir makinede çağırmak isteseyk, örneğin, `ResourceEstimator()` yalnızca kullanacağız `<Q#callable>.estimate_resources(<args>)` .
> Genel olarak, Q # işlemleri çalıştırdıkları makinelere belirsizdir, ancak gibi bazı özellikler `DumpMachine` farklı davranabilirler.

4. Benzetimi gerçekleştirdikten sonra, işlem çağrısı, Q # dosyasında tanımlandığı şekilde değerleri döndürür.
    Şimdilik hiçbir şey döndürülmedi, ancak daha sonra bu değerleri atamaya ve işlemeye yönelik bir örnek görüyoruz.
    Uygulamalı ve tamamen klasik verileri elde ettiğimiz için, beğendiğimiz her şeyi yapabiliriz.

Tam `host.py` dosyanız şu şekilde olmalıdır:

```python
import qsharp
from NamespaceQFT import Perform3qubitQFT

Perform3qubitQFT.simulate()
```

Python dosyasını çalıştırın ve konsolunuza yazdırıldıktan `Message` sonra aşağıdaki ve çıkışları görmeniz gerekir `DumpMachine` . 


#### <a name="c"></a>[C#](#tab/tabid-csharp)

[Install kılavuzundaki](xref:microsoft.quantum.install.cs)ile aynı yönergeleri Izleyerek bir C# konak dosyası oluşturun ve olarak yeniden adlandırın `host.cs` .

C# ana bilgisayarının dört bölümü vardır:
1. Kuantum simülatörünü oluşturma.
    Aşağıdaki kodda, bu değişkendir `qsim` .
2. Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama.
    Bu örnekte hiçbiri yok.
3. Kuantum algoritmasını çalıştırma. 
    Her Q# işlemi aynı adda bir C# sınıfı oluşturur. 
    Bu sınıfın, işlemi **zaman uyumsuz** olarak yürüten bir `Run` yöntemi vardır.
    Yürütmenin zaman uyumsuz olmasının nedeni gerçek donanım üzerindeki yürütmenin zaman uyumsuz yapılacağıdır. 
    `Run`Yöntemi zaman uyumsuz olduğundan, yöntemi çağırıyoruz `Wait()` ; Bu, görev tamamlanana kadar yürütmeyi engeller ve sonucu zaman uyumlu olarak döndürür. 
4. İşlemin döndürülen sonucunu işleyin.
    Şimdilik işlem hiçbir şey döndürmez.


```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                Perform3QubitQFT.Run(qsim).Wait();
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}

```
Uygulamayı çalıştırın ve çıktın aşağıdaki ile eşleşmesi gerekir.
Bir tuşa bastığınızda programdan çıkılır.
***

```Output
Initial state |000>:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
After:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
```

Tam durum simülatörü üzerinde çağrıldığında, `DumpMachine()` hisse Eyaleti 'nin dalga işlevinin bu çoklu gösterimlerini sağlar. Bir $n $-qubit sisteminin olası durumları, her biri karşılık gelen bir karmaşık katsayı (yalnızca genliği ve bir aşama) olan $2 ^ n $ hesaplama tabanlı durumlar ile temsil edilebilir.
Hesaplama tabanlı durumlar, {0} {1} her ikili basamağın tek bir qubit 'e karşılık geldiği, qubit durumlarının $ \tus$ ve $ \ket $ ' nin olası tüm birleşimleri olan $n $---uzunluğunun tüm olası ikili dizelerine karşılık gelir.

İlk satır, karşılık gelen qubits kimlikleri için önemli sırayla bir açıklama sağlar.
`2`"En önemli" olan qubit, taban durum vektörü $ \ket{i} $ öğesinin ikili gösteriminde, qubit durumunun `2` en soldaki basamağa karşılık geldiğini gösterir. Örneğin, $ \ket {6} = \ket $, qubit ve her ikisi de $ \gre$ ' da $ {110} `2` `1` {1} \gre$ ve qubit ' te `0` {0} .


Satırların geri kalanı, hem Kartezyen hem de kutupsal biçimlerdeki temel eyalet vektörü $ \ket{i} $ ölçgenin olasılığını anlatmaktadır.
Giriş durumumuz ilk satırı için ayrıntılı $ \ ayraç {000} $:
* **`|0>:`** Bu satır, `0` Hesaplama esası durumuna karşılık gelir (ilk durum ayırma sonrası $ \ket {000} $ olur, bunun için bu noktada olasılık genliği olan tek durum olması beklenir).
* **`1.000000 +  0.000000 i`**: Kartezyen biçiminde olasılık genliği.
* **` == `**: `equal` işaret, her iki eşdeğer temsili de ayırır.
* **`********************`**: Büyüklük grafik gösterimi, sayısı `*` Bu durum vektörünü ölçme olasılığının müşterinizin istekleriyle orantılı. 
* **`[ 1.000000 ]`**: büyüklük sayısal değeri
* **`    ---`**: Genin aşamasının grafik gösterimi.
* **`[ 0.0000 rad ]`**: aşamanın sayısal değeri (radyan cinsinden).

Büyüklük ve aşama bir grafik gösterimiyle birlikte görüntülenir. Büyüklük temsili basittir: bir çubuğu gösterir `*` ve olasılık arttıkça, çubuk ne kadar büyük olur. Aşama için bkz. [test ve hata ayıklama:](xref:microsoft.quantum.guide.testingdebugging#dump-functions) açı aralıklarına dayanan olası sembol temsilleri için döküm işlevleri.


Bu nedenle, yazdırılan çıktı, programlanmış kapıları durumumuzu dönüştürdüğünü gösterir

$ $ \ket{\psı} \_ {Initial} = \ket {000} $ $

- 

$ $ \begin{hizalaması} \ket{\psı} \_ {final} &= \frac {\sqrt} \left (\ket + \tus+ \tus+ \tus+ \tus+ \ket {1} {8} {000} {001} {010} {011} {100} {101} + \ket {110} + \ ayraç {111} \ sağ) \\ \\ &= \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} \ket{j}, \end{hizalaması} $ $

Bu, 3-qubit Fourier dönüştürmesinin kesin bir davranıştır. 

Diğer giriş durumlarının nasıl etkilendiğini merak ediyorsanız, dönüşümden önce qubit işlemleri uygulamayla birlikte oynamanızı öneririz.

## <a name="adding-measurements"></a>Ölçümler ekleme

Ne yazık ki hisse kuyadan oluşan bir temel taş, gerçek bir hisse sisteminin böyle bir işleve sahip olmadığını bize söyler `DumpMachine` . Bunun yerine, bilgileri ölçümler aracılığıyla ayıklamaya zorlıyoruz. Bu, genel olarak yalnızca bize tam hisse alım durumunu sağlamayarak, ancak sistemin kendisini büyük ölçüde değiştirebilir.
Birçok hisse ölçüm ölçümü vardır ancak tek bir qubit üzerinde en temel: çoklu ölçümler üzerinde odaklanacağız.
Belirli bir temelde ölçülerek (örn. hesaplama tabanlı $ \{ \demet {0} , \demet {1} \} $), qubit durumu, bu nedenle ikisi arasındaki herhangi bir üst konuma yok edilirken, her bir temel duruma göre yansıtılmıştır---.

Bir Q # programı içindeki ölçümleri uygulamak için, `M` `Microsoft.Quantum.Intrinsic` bir türü döndüren (from) işlemini kullanırız `Result` .

İlk olarak, `Perform3QubitQFT` işlem yerine, ölçüm sonuçlarının bir dizisini döndürecek şekilde değişiklik yaptık `Result[]` `Unit` .

```qsharp
    operation Perform3QubitQFT() : Result[] {
```

#### <a name="define-and-initialize-result-array"></a>Diziyi tanımlama ve başlatma `Result[]`

Qubits (yani, `using` deyimden önce) ayırmadan önce bu length 3 diziyi (her bir qubit için bir tane) bildiririz ve bağladık `Result` : 

```qsharp
        mutable resultArray = new Result[3];
```

Kullanım `mutable` öncesi anahtar sözcüğü, `resultArray` değişkenin kod içinde daha sonra yeniden bağlanmasını sağlar---örneğin ölçüm sonuçlarımızı eklerken.

#### <a name="perform-measurements-in-a-for-loop-and-add-results-to-array"></a>Ölçümleri bir döngüde gerçekleştirin `for` ve sonuçları diziye ekleyin

Blok içindeki Fourier dönüştürme işlemlerinden sonra `using` aşağıdaki kodu ekleyin:

```qsharp
            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }
```
[`IndexRange`](xref:microsoft.quantum.arrays.indexrange)Bir dizide çağrılan işlev (örn. qubits dizimiz `qs` ) dizinin dizinlerinin üzerinde bir Aralık döndürür. Burada, `for` ifadesini kullanarak her bir qubit 'i sırayla ölçmek için döngüümüzde kullanırız `M(qs[i])` .
Her ölçülen `Result` tür ( `Zero` ya da `One` ), `resultArray` bir Update ve-yeniden atama ifadesiyle ilgili dizin konumuna eklenir.

> [!NOTE]
> Bu deyimin sözdizimi, Q # için benzersizdir, ancak `resultArray[i] <- M(qs[i])` F # ve R gibi diğer dillerde görülen benzer değişken yeniden atamaya karşılık gelir.

Anahtar sözcüğü, `set` kullanarak değişkenlerin bağlanmasını yeniden atamak için her zaman kullanılır `mutable` .

#### <a name="return-resultarray"></a>Döndürülmesini`resultArray`

Üç qubit ölçülmüş ve sonuçları öğesine eklendiğinde `resultArray` , qubits 'i daha önce sıfırlamak ve serbest bırakmak güvenlidir.
Blok kapatıldıktan sonra `using` Ekle

```qsharp
        return resultArray;
```
son olarak, işlem çıktısını geri döndürür. 

### <a name="understanding-the-effects-of-measurement"></a>Ölçümün etkilerini anlama

`DumpMachine`Ölçümlere daha önce ve sonra durum çıkarmak için işlevlerimizin yerleşimini değiştirelim.
Son işlem kodu şöyle görünmelidir: 

```qsharp
    operation Perform3QubitQFT() : Result[] {

        mutable resultArray = new Result[3];

        using (qs = Qubit[3]) {

            //QFT:
            //first qubit:
            H(qs[0]);
            Controlled R1([qs[1]], (PI()/2.0, qs[0]));
            Controlled R1([qs[2]], (PI()/4.0, qs[0]));

            //second qubit:
            H(qs[1]);
            Controlled R1([qs[2]], (PI()/2.0, qs[1]));

            //third qubit:
            H(qs[2]);

            SWAP(qs[2], qs[0]);

            Message("Before measurement: ");
            DumpMachine();

            for(i in IndexRange(qs)) {
                set resultArray w/= i <- M(qs[i]);
            }

            Message("After measurement: ");
            DumpMachine();

            ResetAll(qs);
        }
        return resultArray;
    }
}
```

Komut satırından çalışıyorsanız, döndürülen dizi yalnızca yürütmenin sonunda konsola doğrudan yazdırılır...
Aksi takdirde, döndürülen diziyi işlemek için ana bilgisayar programınızı güncelleştirin.

#### <a name="command-line"></a>[Komut satırı](#tab/tabid-cmdline)

Konsolda yazdırılacak döndürülen diziyi daha fazla anlamak için, `Message` deyimden hemen önce Q # dosyasına bir tane ekleyebiliriz `return` :

```qsharp
        Message("Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
        return resultArray;
```

Projeyi çalıştırın ve çıktımızda aşağıdakine benzer görünmelidir:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]
```

#### <a name="python"></a>[Python](#tab/tabid-python)

Python programınızı şu şekilde güncelleştirin:

```python
import qsharp
from NamespaceQFT import Perform3QubitQFT

measurementResult = Perform3QubitQFT.simulate()
print("\n")
print("Measured post-QFT state: [qubit0, qubit1, qubit2]")
print(measurementResult)

# reversing order to show corresponding basis state in binary form
binaryCompBasisState = ""
for i in measurementResult:
    binaryCompBasisState = str(i) + binaryCompBasisState
print("Corresponding basis state in binary:")
print("|" + binaryCompBasisState + ">")
```

Dosyasını çalıştırın ve çıktlarınızın aşağıdakine benzer olması gerekir:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]                   

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[1, 1, 0]

Corresponding basis state in binary:
|011>
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

İşlem bir sonuç döndürdüğünü artık, özelliği getirilirken yöntem çağrısını değiştirin `Wait()` `Result` . Bu, daha önce bahsedilen aynı eşitlemeyi yine de gerçekleştirir ve bu değeri doğrudan değişkene bağlayabiliriz `measurementResult` .

```csharp
using System;

using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace NamespaceQFT
{
    class Driver
    {
        static void Main(string[] args)
        {
            using (var qsim = new QuantumSimulator())
            {
                var measurementResult = Perform3QubitQFT.Run(qsim).Result;
                System.Console.WriteLine(
                    $"Post-QFT measurement results [qubit0, qubit1, qubit2]: ");
                System.Console.WriteLine(
                    measurementResult);

                // reversing order to show corresponding basis state in binary form
                string binaryCompBasisState = String.Empty;

                foreach (Result i in measurementResult)
                {
                    string iString = i.ToString();
                    binaryCompBasisState = iString + binaryCompBasisState;
                }
                binaryCompBasisState = "|" + binaryCompBasisState + ">";
                System.Console.WriteLine(
                    $"Corresponding basis state in binary:");
                System.Console.WriteLine(
                    binaryCompBasisState);
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
        }
    }
}
```

Projeyi çalıştırın ve çıktımızda aşağıdakine benzer görünmelidir:

```Output
Before measurement: 
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|1>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|2>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|3>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|4>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|5>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|6>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
|7>:     0.353553 +  0.000000 i  ==     ***                  [ 0.125000 ]     --- [  0.00000 rad ]
After measurement:
# wave function for qubits with ids (least to most significant): 0;1;2
|0>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|1>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|2>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|3>:     1.000000 +  0.000000 i  ==     ******************** [ 1.000000 ]     --- [  0.00000 rad ]
|4>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|5>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|6>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]
|7>:     0.000000 +  0.000000 i  ==                          [ 0.000000 ]

Post-QFT measurement results [qubit0, qubit1, qubit2]: 
[One,One,Zero]

Corresponding basis state in binary:
|ZeroOneOne>

Press any key to continue...
```
***

Bu çıktı birkaç farklı şeyi gösterir:
1. Döndürülen sonucu ön ölçüyle karşılaştıran `DumpMachine` , bu durum, temel olarak son _not_ olarak QFT üst konumunu göstermez.
    Ölçüm, sistemin dalga işlevindeki bu durumun genliğini tespit eden bir olasılık ile yalnızca tek bir temel durum döndürür.
2. Ölçüm sonrası `DumpMachine` , ölçümün durumunun kendisini _değiştirmekte_ olduğunu görüyoruz ve bu ölçüyü, ilk üst konumdan temel durumlar üzerinden, ölçülen değere karşılık gelen tek başına duruma yansıdık.

Bu işlemi birçok kez tekrarlıyoruz, sonuç istatistiklerinin, her bir görüntüsündeki rastgele sonuca artmaya yönelik QFT durumunun eşit ağırlıklı konumunu göstermeye başladığımızda görüyoruz.
_Ancak_, verimsiz olmasının yanı sıra yine de, bu, aralarındaki göreli aşamalara göre değil, yalnızca temel durumların göreli bir şekilde yeniden oluşturulmasını ister.
İkincisi bu örnekteki bir sorun değildir, ancak QFT 'ye $ \ket $ ' den daha karmaşık bir giriş verildiyse, göreli aşamalar görüneceğiz {000} .

#### <a name="partial-measurements"></a>Kısmi ölçümler 
Kaydın yalnızca bazı qubits 'in sistem durumunu nasıl etkileyebileceğini öğrenmek için, `for` ölçüm satırından sonra, döngünün içine aşağıdakileri eklemeyi deneyin:
```qsharp
                let iString = IntAsString(i);
                Message("After measurement of qubit " + iString + ":");
                DumpMachine();
```

Eklemeniz gereken işleve erişmek için `IntAsString` 
```qsharp
    open Microsoft.Quantum.Convert;
```
diğer ad alanı `open` deyimleriyle.

Sonuçta elde edilen çıktıda, her bir qubit ölçülerek dereceli projeksiyonları alt boşluklara görürsünüz.


## <a name="use-the-q-libraries"></a>Q # kitaplıklarını kullanma
Giriş bölümünde bahsedildiği gibi, Q # gücünün büyük bir bölümü, tek bir qubits ile ilgilenme dünyadan yararlanın.
Gerçekten de, tam ölçekli, uygun hisse programları geliştirmek istiyorsanız, `H` belirli bir dönüşten önce veya sonra bir işlemin, yalnızca sizi yavaşlatıp yavaşlamadığını endişelenmeniz gerekir. 

Q # kitaplıkları, herhangi bir sayıda qubit için yalnızca uygulayabileceğiniz ve uygulayabileceğiniz [QFT](xref:microsoft.quantum.canon.qft) işlemini içerir.
Denemek için, Q # dosyanızda aynı içeriğe sahip olan `Perform3QubitQFT` , ancak ilk `H` `SWAP` yerine iki kolay satıra sahip olan her şeyi içeren yeni bir işlem tanımlayın:
```qsharp
            let register = BigEndian(qs);    //from Microsoft.Quantum.Arithmetic
            QFT(register);                   //from Microsoft.Quantum.Canon
```
İlk satır yalnızca, [`BigEndian`](xref:microsoft.quantum.arithmetic.bigendian) `qs` [QFT](xref:microsoft.quantum.canon.qft) işleminin bağımsız değişken olarak aldığı bir qubit dizisinin ayrılmış dizisinin bir ifadesini oluşturur.
Bu, kayıttaki qubits 'in Dizin sıralamasına karşılık gelir.

Bu işlemlere erişebilmek için, `open` Q # dosyasının başlangıcında ilgili ad alanları için deyimler ekleyin:
```qsharp
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Arithmetic;
```

Şimdi, ana bilgisayar programınızı yeni işleminizi (ör.) çağırmak için ayarlayın `PerformIntrinsicQFT` ve bir yanıt verin.

Q # kitaplığı işlemlerini kullanmanın gerçek avantajını görmek için, qubit sayısını dışında bir şekilde değiştirin `3` :
```qsharp
        mutable resultArray = new Result[4]; 

        using (qs = Qubit[4]) {
            //...
        }
```
Bu nedenle, `H` her bir qubit üzerinde yeni işlemler ve döndürmeler hakkında endişelenmenize gerek kalmadan, belirli sayıda qubit için uygun QFT 'leri uygulayabilirsiniz.

Hisse senedi simülatörü, gerçek hisse donanımı için neden ilerletireceğiz kesin olarak---, tam olarak çalışır şekilde daha fazla zaman kaplar!













