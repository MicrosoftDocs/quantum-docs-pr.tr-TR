---
title: Q# ile dolanıklığı keşfetme
description: Q# dilinde kuantum programı yazmayı öğrenin. Quantum Development Kit'i (QDK) kullanarak Bell Durumu uygulaması geliştirme
author: natke
ms.author: nakersha
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 989080e7d9979bb87d14b2580d28732bb1092eb1
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327382"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Öğretici: Q\# ile dolaşıklığı keşfetme

Bu öğreticide, kubitleri düzenleyip ölçen ve süper konum ile dolaşıklığın etkilerini gösteren bir Q# programının nasıl yazılacağı gösterilir.
Bu rehber QDK'yı yükleme, programı oluşturma ve bir kuantum simülatörü üzerinde yürütme konusunda size yol gösterecektir.  

Kuantum dolaşıklığı göstermek için Bell adında bir uygulama yazacaksınız.
Bell adı, en basit süper konum ve kuantum dolaşıklığı örneklerini göstermek için kullanılan iki kubitin belirli kuantum durumları olan Bell durumlarını ifade eder.

## <a name="pre-requisites"></a>Ön koşullar

Kodlamaya başlamaya hazırsanız devam etmeden önce şu adımları izleyin: 

* [Python](xref:microsoft.quantum.install.python) veya [.NET](xref:microsoft.quantum.install.cs) için Quantum geliştirme setini yükleyin.
* Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun

Dilerseniz QDK'yı yüklemeden anlatımı takip ederek Q# programlama diline genel bir bakış elde edebilir ve kuantum bilişiminin ilk kavramlarını öğrenebilirsiniz.

## <a name="demonstrating-qubit-behavior-with-q"></a>Q# ile kubit davranışını gösterme

Basit [kubit tanımımızı](xref:microsoft.quantum.overview.understanding) hatırlayalım.  Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, [kubitin](xref:microsoft.quantum.glossary#qubit) durumu 0 ve 1’in bir **süper konumunda** olabilir.  Kavramsal olarak bir kubit, boşluktaki bir yön (vektör olarak da bilinir) olarak düşünülebilir.  Bir kubit herhangi bir yönde olabilir. İki **klasik durum**, iki yöndür. Bu da %100 oranında 0 ölçme şansını ve %100 oranında 1 ölçme şansını gösterir.  Bu gösterim ayrıca [Bloch küresi](/quantum/concepts/the-qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) ile daha anlaşılır bir şekilde gösterilmiştir.

Ölçüm işlemi ikili sonuç üretir ve bir kubit durumunu değiştirir. Ölçüm, 0 veya 1 ikili değerini verir.  Kubit, süper konumdan (herhangi bir yöne) klasik durumlardan birine geçer.  Bundan sonra aynı ölçümün başka bir işlemle müdahale edilmeden yinelenmesi durumunda aynı ikili sonuç ortaya çıkar.  

Birden çok kubit [**dolaşık hale getirilebilir**](xref:microsoft.quantum.glossary#entanglement). Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.

Şimdi bu davranışın Q# ile nasıl ifade edildiğine bakalım.  Mümkün olan en basit programla başlayıp kuantum süper konumu ile kuantum dolaşıklığını göstermek için bunu geliştirirsiniz.

## <a name="setup"></a>Kurulum

Bu öğretici, bir konak program kullanır ve iki bölümden oluşur:

1. Q# kuantum programlama dili kullanılarak uygulanan bir dizi kuantum algoritması.
1. Python veya C# gibi bir dilde uygulanan, ana giriş noktası işlevi gören ve kuantum algoritmalarını yürütmek üzere Q# işlemlerini çağıran bir konak program.

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Uygulamanız için bir konum seçin

1. `Bell.qs` adlı bir dosya oluşturun. Bu dosya Q# kodunuzu içerecektir.

1. `host.py` adlı bir dosya oluşturun. Bu dosya Python konak kodunuzu içerecektir.

#### <a name="c-command-line"></a>[C# Komut Satırı](#tab/tabid-csharp)

1. Yeni Q# projesi oluşturma:

    ```bash
    dotnet new console -lang Q# --output Bell
    cd Bell
    ```

    `.csproj` dosyasını, `Operations.qs` adlı Q# dosyasını ve `Driver.cs` adlı konak programını görüyor olmalısınız

1. Q# dosyasını yeniden adlandırın

    ```bash
    mv Operation.qs Bell.qs
    ```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Yeni bir proje oluşturma

   * Visual Studio’yu açın
   * **Dosya** menüsüne gidin ve **Yeni** -> **Proje...** öğesini seçin.
   * Proje şablonu gezginindeki arama alanına `Q#` yazın ve `Q# Application` şablonunu seçin
   * Projenize `Bell` adını verin

1. Q# dosyasını yeniden adlandırın

   * **Çözüm Gezgini**'ne gidin
   * `Operations.qs` dosyasına sağ tıklayın
   * Dosyayı `Bell.qs` olarak yeniden adlandırın

* * *

## <a name="write-a-q-operation"></a>Q# işlemi yazma

Burada hedefimiz, belirli bir kuantum durumunda iki kubit hazırlayarak Q# ile kubitlerin durumunu değiştirme işlemlerinin yanı sıra süper konum ve dolaşıklık etkilerini göstermektir. Kubit durumlarını, işlemleri ve ölçümü göstermek için bunu parça parça oluşturacağız.

**Genel bakış:**  Aşağıdaki ilk kodda Q# içinde kubitlerle nasıl çalışacağınız gösterilmektedir.  Bir kubitin durumunu değiştiren iki işlem olan `M` ve `X` işlemlerini tanıtacağız. 

Bu kod parçacığında parametre olarak bir kubit ile kubitin içinde bulunmasını istediğimiz durumu temsil eden `desired` parametresini alan `Set` işlemi tanımlanmıştır.  `Set` işlemi, `M` işlemini kullanarak kubit üzerinde bir ölçüm gerçekleştirir.  Q# dilinde bir kubit ölçümü her zaman `Zero` veya `One` döndürür.  Ölçümün istenen değere eşit olmayan bir değer döndürmesi halinde Set işlemi kubiti "çevirir". Bu durumda bir `X` işlemi yürüterek kubit durumunu ölçümün `Zero` ve `One` döndürme olasılıklarının tersine çevrilmiş olduğu yeni bir durum olarak değiştirir.  Sonrasında `Set` işleminin etkisini göstermek için bir `TestBellState` işlemi eklenir.  Bu işlem giriş olarak `Zero` veya `One` alır. Ardından `Set` işlemini bu girişle birkaç kez çağırıp kubitin ölçümünden döndürülen `Zero` sayısı ile döndürülen `One` sayısını hesaplar. Elbette bu ilk `TestBellState` işlemi simülasyonunda çıkışın parametre girişi `Zero` döndüreceğinden, tüm kubit ölçümlerinin `Zero` ile ayarlanmış olduğunu ve parametre girişi `One` döndüreceğinden tüm kubit ölçümlerinin `One` ile ayarlanmış olduğunu göstermesi beklenir.  Sonrasında süper konumu ve dolaşıklığı göstermek için `TestBellState` içine kod ekleyeceğiz.


### <a name="q-operation-code"></a>Q# işlem kodu

1. Bell.qs dosyasının içeriğini aşağıdaki kodla değiştirin:

    ```qsharp
    namespace Quantum.Bell {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation Set(desired : Result, q1 : Qubit) : Unit {
            if (desired != M(q1)) {
                X(q1);
            }
        }
    }
    ```

    Bu işlem artık kubiti klasik bir duruma getirerek %100 `Zero` veya %100 `One` döndürmesi sağlanabilir.  `Zero` ve `One`, bir kubit ölçümünün mümkün olan iki sonucunu gösteren sabitlerdir.

    `Set` işlemi kubiti ölçer.
    Kubit istediğimiz durumdaysa `Set` başka bir işlem gerçekleştirmez, değilse `X` işlemini çalıştırarak kubitin durumunu istediğimiz duruma getirebiliriz.

### <a name="about-q-operations"></a>Q# işlemleri hakkında

Q# işlemi bir kuantum alt yordamıdır. Başka bir deyişle kuantum işlemlerini içeren çağrılabilir bir yordamdır.

İşlemin bağımsız değişkenleri parantez içinde tanımlama grubu olarak belirtilir.

Bir iki nokta işareti eklendikten sonra işlemin dönüş türü belirtilir. Bu örnekte `Set` işleminin dönüşü yoktur, dolayısıyla `Unit` döndürüyor olarak işaret edilir. Bu F# dilindeki `unit` öğesinin Q# eşdeğeridir, kabaca C# dilindeki `void` ve Python'daki boş bir tanımlama grubuyla (`Tuple[()]`) karşılaştırılabilir.

İlk Q# işleminizde iki kuantum işlemi kullandınız:

* Kubitin durumunu ölçen [M](xref:microsoft.quantum.intrinsic.m) işlemi
* Kubitin durumunu çeviren [X](xref:microsoft.quantum.intrinsic.x) işlemi

Kuantum işlemi, kubitin durumunu dönüştürür. Bazen kuantum işlemleri, klasik mantıksal geçitlere benzetildiğinden geçit olarak adlandırılır. Bu kullanım kuantum bilgisayarların ilk dönemlerine dayanır. Bu dönemde algoritmaların yalnızca teorik yapılardı ve klasik bilgi işlem devre şemalarına benzer şekilde görselleştirilirdi.

### <a name="add-q-test-code"></a>Q# test kodu ekleme

1. Aşağıdaki işlemi `Bell.qs` dosyasında ad alanının içine, `Set` işleminin sonuna ekleyin:

    ```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                Set(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            Set(Zero, qubit);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
    ```

    Bu işlem (`TestBellState`) `count` yinelemeleri için döngü yapar, bir kubitte belirtilen `initial` değerini ayarlar ve ardından sonucu ölçer (`M`). Kaç sıfır ve bir ölçtüğümüzle ilgili istatistikleri toplar ve bunları çağrıyı yapana döndürür. Bir gerekli işlem daha gerçekleştirir. Kubiti döndürmeden önce bilinen bir duruma (`Zero`) sıfırlayarak diğerlerinin bu kubiti bilinen durumda ayırmasına olanak tanır. Bu, `using` deyimi için gereklidir.

### <a name="about-variables-in-q"></a>Q# dilindeki değişkenler hakkında

Varsayılan olarak Q# dilinde değişkenler sabittir; bunların değeri bağlandıktan sonra değiştirilemez. Sabit bir değişkenin bağlamasını göstermek için `let` anahtar sözcüğü kullanılır. İşlem bağımsız değişkenleri her zaman sabittir.

Değeri değişebilen `numOnes` gibi bir değişkene ihtiyacınız varsa değişkeni `mutable` anahtar sözcüğüyle bildirebilirsiniz. Değişebilir değişkenin değeri `set` deyimi kullanılarak değiştirilebilir.

Her iki durumda da, değişkenin türü derleyici tarafından çıkarsanır. Q# dilinde değişkenler için herhangi bir türde ek açıklama gerekmez.

### <a name="about-using-statements-in-q"></a>Q# dilindeki `using` deyimleri hakkında

Q# dilinde `using` deyimi de özeldir. Kubitleri bir kod bloğunda kullanım amacıyla ayırmak için kullanılır. Q# dilinde tüm kubitler dinamik olarak ayrılır ve serbest bırakılır; karmaşık bir algoritmanın tüm yaşam süresi boyunca orada olan sabit kaynaklar değillerdir. Başlangıçta `using` deyimi bir kubit kümesi ayırır ve bloğun sonunda bu kubitleri serbest bırakır.

## <a name="create-the-host-application-code"></a>Konak uygulama kodunu oluşturma

#### <a name="python"></a>[Python](#tab/tabid-python)

1. `host.py` dosyasını açın ve aşağıdaki kodu ekleyin:

    ```python
    import qsharp

    from qsharp import Result
    from Quantum.Bell import TestBellState

    initials = (Result.Zero, Result.One)

    for i in initials:
      res = TestBellState.simulate(count=1000, initial=i)
      (num_zeros, num_ones) = res
      print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4}')
    ```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

1. `Driver.cs` dosyasının içeriğini aşağıdaki kodla değiştirin:

    ```csharp
    using System;

    using Microsoft.Quantum.Simulation.Core;
    using Microsoft.Quantum.Simulation.Simulators;

    namespace Quantum.Bell
    {
        class Driver
        {
            static void Main(string[] args)
            {
                using (var qsim = new QuantumSimulator())
                {
                    // Try initial values
                    Result[] initials = new Result[] { Result.Zero, Result.One };
                    foreach (Result initial in initials)
                    {
                        var res = TestBellState.Run(qsim, 1000, initial).Result;
                        var (numZeros, numOnes) = res;
                        System.Console.WriteLine(
                            $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4}");
                    }
                }

                System.Console.WriteLine("Press any key to continue...");
                Console.ReadKey();
            }
        }
    }
    ```

#### [](#tab/tabid-vs2019)

* * *

### <a name="about-the-host-application-code"></a>Konak uygulama kodu hakkında

#### <a name="python"></a>[Python](#tab/tabid-python)

Python konak uygulamasının üç bölümü vardır:

* Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama. Örnekte `count` 1000 değerine sabitlenmiştir ve `initial` kubitin ilk değeridir.
* İçeri aktarılan Q# işleminin `simulate()` yöntemini çağırarak kuantum algoritmasını çalıştırma.
* İşlemin sonucunu işleme. Örnekte işlemin sonucunu `res` alır. Burada sonuç, simülatör tarafından hesaplanan sıfırların sayısından (`num_zeros`) ve birlerin sayısından (`num_ones`) oluşmuş bir tanımlama grubudur. Tanımlama grubunu ayrıştırıp iki alan elde eder ve sonuçları yazdırırız.

#### <a name="c"></a>[C#](#tab/tabid-csharp)

C# konak uygulamasının dört bölümü vardır:

* Kuantum simülatörünü oluşturma. Örnekte simülatör olarak `qsim` kullanılmıştır.
* Kuantum algoritması için gereken tüm bağımsız değişkenleri hesaplama. Örnekte `count` 1000 değerine sabitlenmiştir ve `initial` kubitin ilk değeridir.
* Kuantum algoritmasını çalıştırma. Her Q# işlemi aynı adda bir C# sınıfı oluşturur. Bu sınıfın, işlemi **zaman uyumsuz** olarak yürüten bir `Run` yöntemi vardır. Yürütmenin zaman uyumsuz olmasının nedeni gerçek donanım üzerindeki yürütmenin zaman uyumsuz yapılacağıdır. `Run` yöntemi zaman uyumsuz olduğundan `Result` özelliğini getiririz; bu özellik, görev tamamlanana ve zaman uyumlu olarak sonucu döndürene kadar yürütmeyi engeller.
* İşlemin sonucunu işleme. Örnekte işlemin sonucunu `res` alır. Burada sonuç, simülatör tarafından hesaplanan sıfırların sayısından (`numZeros`) ve birlerin sayısından (`numOnes`) oluşmuş bir tanımlama grubudur. Bu sonuç C# dilinde ValueTuple olarak döndürülür. Tanımlama grubunu ayrıştırıp iki alan elde eder, sonuçları yazdırır ve tuşa basılmasını bekleriz.

#### [](#tab/tabid-vs2019)

* * *

## <a name="build-and-run"></a>Derleme ve çalıştırma

#### <a name="python"></a>[Python](#tab/tabid-python)

1. Terminalinizde aşağıdaki komutu çalıştırın:

    ```
    python host.py
    ```

    Bu komut Q# işleminin benzetimini yapan konak uygulamayı çalıştırır.

Sonuçlar şöyle olmalıdır:

```Output
Init:0    0s=1000 1s=0   
Init:1    0s=0    1s=1000
```

#### <a name="command-line--visual-studio-code"></a>[Komut Satırı / Visual Studio Code](#tab/tabid-csharp)

1. Terminalinizde aşağıdaki komutu çalıştırın:

    ```bash
    dotnet run
    ```

    Bu komut otomatik olarak tüm gerekli paketleri indirir, uygulamayı derler ve sonra da bunu komut satırında çalıştırır.

1. Alternatif olarak **F1** tuşuna basarak Komut Paletini açın ve **Hata Ayıkla: Hata Ayıklama Olmadan Başlat**'ı seçin.
Programın nasıl başlatılacağını açıklayan yeni bir ``launch.json`` dosyası oluşturmanız istenebilir.
Çoğu uygulama için varsayılan ``launch.json`` dosyası yeterli olacaktır.

Sonuçlar şöyle olmalıdır:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

#### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs2019)

1. Yalnızca `F5` tuşuna basın, programınız derlenir ve çalıştırılır!

Sonuçlar şöyle olmalıdır:

```Output
Init:Zero 0s=1000 1s=0
Init:One  0s=0    1s=1000
Press any key to continue...
```

Bir tuşa bastığınızda programdan çıkılır.

* * *

## <a name="prepare-superposition"></a>Süper konumu hazırlama

**Genel bakış** Şimdi Q# dilinin kubitleri süper konuma alma şeklini nasıl ifade ettiğine bakalım.  Hatırlayacağınız gibi bir kubit 0 ve 1 süper konumlarında olabilir.  Bunu gerçekleştirmek için `Hadamard` işlemini kullanacağız. Kubitin klasik durumlardan birine olması halinde (ölçümün her zaman `Zero` veya her zaman `One` döndürmesi durumunda) `Hadamard` ya da `H` işlemi kubiti ölçümün %50 oranında `Zero` ve %50 oranında `One` döndüreceği bir duruma alır.  Kavramsal olarak kubitin `Zero` ile `One` arasındaki bir noktada olduğu düşünülebilir.  Şimdi `TestBellState` işleminin simülasyonunu yaptığımızda, ölçüm sonrasında elde edilen sonuçların `Zero` ve `One` için yaklaşık olarak eşit değerler verdiğini göreceğiz.  

İlk olarak kubiti çevirmeyi deneyeceğiz. (Kubit `Zero` durumundaysa `One` durumuna çevireceğiz veya aksi halde işlemin tam tersini yapacağız.) Bu, kubiti `TestBellState` işleminde ölçmeden önce bir `X` işlemi gerçekleştirilerek yapılır:

```qsharp
X(qubit);
let res = M(qubit);
```

Şimdi sonuçlar (`F5` tuşuna basıldıktan sonra) tersine çevrilir:

```Output
Init:Zero 0s=0    1s=1000
Init:One  0s=1000 1s=0
```

Ama şimdiye kadar gördüğümüz her şey klasikti. Şimdi de bir kuantum sonucu alalım. Önceki çalıştırmadaki `X` işlemini bir `H` veya Hadamard işlemiyle değiştirmemiz yeterli olacaktır. Kubiti 0'dan 1'e kadar tümüyle çevirmek yerine yalnızca yarı yola kadar çevireceğiz. `TestBellState` işleminde değiştirilen satırlar şöyle görünür:

```qsharp
H(qubit);
let res = M(qubit);
```

Daha ilginç sonuçlar görülmeye başlar:

```Output
Init:Zero 0s=484  1s=516
Init:One  0s=522  1s=478
```

Her ölçtüğümüzde klasik bir değer bekleriz ama kubit 0 ile 1 arasında yarı yoldadır, dolayısıyla (istatistiksel olarak) ölçülerin yarısında 0 ve yarısında da 1 elde ederiz. Bu __süper konum__ olarak bilinir ve bize kuantum durumunun ilk gerçek görünümünü verir.

## <a name="prepare-entanglement"></a>Dolaşıklığı hazırlama

**Genel bakış:**  Şimdi Q# ile kubitleri dolaşık hale getirme işleminin nasıl ifade edildiğine bakalım.  İlk olarak kubiti başlangıç durumuna getireceğiz ve ardından `H` işlemini kullanarak süper konuma alacağız.  Ardından, ilk kubiti ölçmeden önce Controlled-Not (Kontrollü Değil) anlamına gelen yeni bir işlem (`CNOT`) kullanacağız.  Bu işlemi yürütmenin iki kubit üzerindeki sonucu, birinci kubitin `One` olması durumunda ikinci kubiti çevirmektir.  Şimdi iki kubit de dolaşık hale geldi.  İlk kubit için istatistiklerimiz değişmemiştir (ölçüm sonrasında `Zero` veya `One` olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. `CNOT` geçidimiz iki kubiti dolaşık hale getirmiş, bu şekilde ilkine olanın aynısı diğerine de olmuştur. Ölçümleri ters çevirirseniz (ilk kubitten önce ikincisini yaparsanız), aynı durum ortaya çıkar. İlk ölçüm rastgele olacak ve ikincisi ilkinde bulunanla aynı yolu izleyecektir.

İlk yapmamız gereken `TestBellState` işlemine bir kubit yerine 2 kubit ayırmaktır:

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Bu sayede `TestBellState` işleminde ölçüm yapmadan (`M`) önce yeni bir işlem (`CNOT`) ekleyebileceğiz:

```qsharp
Set(initial, q0);
Set(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

İlk kubiti başlatarak, başladığımızda kubitin her zaman `Zero` durumunda olduğundan emin olmak için bir `Set` işlemi daha eklemiştik.

Serbest bırakmadan önce ikinci kubiti de sıfırlamamız gerekiyor.

```qsharp
Set(Zero, q0);
Set(Zero, q1);
```

Yordamın tamamı şimdi şöyle görünür:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set (initial, q0);
                Set (Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes);
    }
```

Bunu çalıştırırsak yine daha önce aldığımız 50-50 sonucunun aynısını alırız. Öte yandan biz, ölçülen ilk kubite ikinci kubitin nasıl tepki gösterdiğiyle ilgileniyoruz. Bu istatistiği `TestBellState` işleminin yeni bir sürümüyle ekleriz:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int, Int) {
        mutable numOnes = 0;
        mutable agree = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                Set(initial, q0);
                Set(Zero, q1);

                H(q0);
                CNOT(q0, q1);
                let res = M(q0);

                if (M(q1) == res) {
                    set agree += 1;
                }

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }
            
            Set(Zero, q0);
            Set(Zero, q1);
        }

        // Return number of times we saw a |0> and number of times we saw a |1>
        return (count-numOnes, numOnes, agree);
    }
```

Yeni dönüş değeri (`agree`), ilk kubitten gelen ölçümün ikinci kubitin ölçümüyle her eşleşmesinin kaydını tutar. Ayrıca konak uygulamayı buna göre güncelleştirmemiz gerekir:

#### <a name="python"></a>[Python](#tab/tabid-python)

```python
import qsharp

from qsharp import Result
from Quantum.Bell import TestBellState

initials = {Result.Zero, Result.One} 

for i in initials:
    res = TestBellState.simulate(count=1000, initial=i)
    (num_zeros, num_ones, agree) = res
    print(f'Init:{i: <4} 0s={num_zeros: <4} 1s={num_ones: <4} agree={agree: <4}')
```

#### <a name="c"></a>[C#](#tab/tabid-csharp)

```csharp
            using (var qsim = new QuantumSimulator())
            {
                // Try initial values
                Result[] initials = new Result[] { Result.Zero, Result.One };
                foreach (Result initial in initials)
                {
                    var res = TestBellState.Run(qsim, 1000, initial).Result;
                    var (numZeros, numOnes, agree) = res;
                    System.Console.WriteLine(
                        $"Init:{initial,-4} 0s={numZeros,-4} 1s={numOnes,-4} agree={agree,-4}");
                }
            }
            
            System.Console.WriteLine("Press any key to continue...");
            Console.ReadKey();
```

#### [](#tab/tabid-vs2019)

* * *

Artık çalıştırdığımızda çok şaşırtıcı bir şey elde ederiz:

```Output
Init:Zero 0s=499  1s=501  agree=1000
Init:One  0s=490  1s=510  agree=1000
```

Genel bakışta belirtildiği üzere ilk kubit için istatistiklerimiz değişmemiştir (0 veya 1 olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. Bunun nedeni bu kubitlerin dolaşık olmasıdır!

Tebrikler, ilk kuantum programınızı yazdınız!

## <a name="next-steps"></a>Sonraki adımlar

[Grover araması](xref:microsoft.quantum.quickstarts.search) başlıklı öğreticide kuantum bilişiminin en popüler algoritmalarından biri olan Grover aramasını oluşturup çalıştırma adımları gösterilir ve kuantum bilişimiyle gerçek sorunları çözmek için kullanılabilecek güzel bir Q# programı örneği sunulur.  

[Quantum Geliştirme Seti'ni Kullanmaya Başlama](xref:microsoft.quantum.welcome) sayfasında, Q# dilini ve kuantum programlamayı öğrenmek için başvurabileceğiniz diğer yöntemlerle ilgili öneriler sunulur.
