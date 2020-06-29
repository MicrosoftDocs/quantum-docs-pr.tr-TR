---
title: Q# ile dolanıklığı keşfetme
description: Q# dilinde kuantum programı yazmayı öğrenin. Quantum Development Kit'i (QDK) kullanarak Bell Durumu uygulaması geliştirme
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
ms.openlocfilehash: 16c93b3dd17363c06602529cb34e8fc84aadc7a8
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415431"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Öğretici: Q\# ile dolaşıklığı keşfetme

Bu öğreticide, kubitleri düzenleyip ölçen ve süper konum ile dolaşıklığın etkilerini gösteren bir Q# programının nasıl yazılacağı gösterilir.

Kuantum dolaşıklığı göstermek için Bell adında bir uygulama yazacaksınız.
Bell adı, en basit süper konum ve kuantum dolaşıklığı örneklerini göstermek için kullanılan iki kubitin belirli kuantum durumları olan Bell durumlarını ifade eder.

## <a name="pre-requisites"></a>Ön koşullar

Kodlamaya başlamaya hazırsanız devam etmeden önce şu adımları izleyin: 

* [Install](xref:microsoft.quantum.install) Tercih ettiğiniz dil ve geliştirme ortamınızı kullanarak hisse geliştirme setini kullanın.
* Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun

Ayrıca, Q # programlama dilinin genel bakışlarını ve hisse bilgi işlem kavramlarının ilk kavramlarını gözden geçirmek için QDK 'yi yüklemeden anlatıcı olarak da izleyebilirsiniz.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Bu öğreticide şunların nasıl yapıldığını öğreneceksiniz:

> [!div class="checklist"]
> * Q 'da işlem oluşturma ve birleştirme\#
> * Qubits 'i üst konuma yerleştirmek için işlemler oluşturun, bunları zenginedin ve ölçün.
> * Bir benzeticide bir Q # programı çalıştırması ile hisse entanglement 'i gösterir. 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>QDK ile qubit davranışı gösterme

Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, [kubitin](xref:microsoft.quantum.glossary#qubit) durumu 0 ve 1’in bir **süper konumunda** olabilir.  Kavramsal olarak, bir qubit durumu soyut bir alanda (vektör olarak da bilinir) bir yön olarak düşünülebilir.  Bir qubit durumu olası yönlere ait olabilir. İki **klasik durum**, iki yöndür. Bu da %100 oranında 0 ölçme şansını ve %100 oranında 1 ölçme şansını gösterir.

Ölçüm işlemi ikili sonuç üretir ve bir kubit durumunu değiştirir.
Ölçüm, 0 veya 1 olan bir ikili değer üretir.  Kubit, süper konumdan (herhangi bir yöne) klasik durumlardan birine geçer.  Bundan sonra aynı ölçümün başka bir işlemle müdahale edilmeden yinelenmesi durumunda aynı ikili sonuç ortaya çıkar.  

Birden çok kubit [**dolaşık hale getirilebilir**](xref:microsoft.quantum.glossary#entanglement).  Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.

Şimdi bu davranışın Q# ile nasıl ifade edildiğine bakalım.  Mümkün olan en basit programla başlayıp kuantum süper konumu ile kuantum dolaşıklığını göstermek için bunu geliştirirsiniz.

## <a name="creating-a-q-project"></a>Bir Q # projesi oluşturma

Yapmanız gereken ilk şey yeni bir Q # projesi oluşturmaktır. Bu öğreticide, [vs Code ile komut satırı uygulamalarına](xref:microsoft.quantum.install.standalone)göre ortamı kullanacağız.

Yeni bir proje oluşturmak için VS Code: 

1. Komut **paletini görüntüle**' ye tıklayın  ->  **Command Palette** ve **Q #: yeni proje oluştur**' u seçin.
2. **Tek başına konsol uygulaması**' na tıklayın.
3. Projeyi kaydetmek için konuma gidin ve **proje oluştur**' a tıklayın.
4. Proje başarıyla oluşturulduğunda, sağ alt köşedeki **Yeni proje... aç** ' a tıklayın.

Bu durumda proje çağırılır `Bell` . Bu iki dosya oluşturur: `Bell.csproj` , proje dosyası ve `Program.qs` uygulamamızı yazmak için kullandığımız bir Q # uygulamasının şablonu. İçeriği şu `Program.qs` olmalıdır:

```qsharp
   namespace Bell {

      open Microsoft.Quantum.Canon;
      open Microsoft.Quantum.Intrinsic;
    

      @EntryPoint()
      operation HelloQ() : Unit {
          Message("Hello quantum world!");
      }
   }
```

## <a name="write-the-q-application"></a>Q uygulamasını yazma \#
 
Burada hedefimiz, belirli bir kuantum durumunda iki kubit hazırlayarak Q# ile kubitlerin durumunu değiştirme işlemlerinin yanı sıra süper konum ve dolaşıklık etkilerini göstermektir. Bu parçaları, qubit durumları, işlemleri ve ölçümü tanıtmak için bir parça oluşturacak şekilde oluşturacağız.

### <a name="initialize-qubit-using-measurement"></a>Ölçüyü kullanarak qubit Başlat

Aşağıdaki ilk kodda Q# içinde kubitlerle nasıl çalışacağınız gösterilmektedir.  İki işlem tanıtıyoruz [`M`](xref:microsoft.quantum.intrinsic.m) ve [`X`](xref:microsoft.quantum.intrinsic.x) bir qubit durumunu dönüştürecek. Bu kod parçacığında parametre olarak bir kubit ile kubitin içinde bulunmasını istediğimiz durumu temsil eden `desired` parametresini alan `SetQubitState` işlemi tanımlanmıştır.  `SetQubitState` işlemi, `M` işlemini kullanarak kubit üzerinde bir ölçüm gerçekleştirir.  Q # içinde, qubit ölçümü her zaman ya da `Zero` döndürür `One` .  Ölçüm, istenen değere eşit olmayan bir değer döndürürse, `SetQubitState` "qubit" değerini çevirir; diğer bir deyişle, bir işlem yürütür ve bu, `X` qubit durumunu, bir ölçünün döndürdüğü ve geri döndürüldüğü yeni bir duruma geçirir `Zero` `One` . Bu şekilde, `SetQubitState` her zaman hedef qubit 'i istenen duruma geçirir.

İçeriğini `Program.qs` aşağıdaki kodla değiştirin:


```qsharp
   namespace Bell {
       open Microsoft.Quantum.Intrinsic;
       open Microsoft.Quantum.Canon;

       operation SetQubitState(desired : Result, q1 : Qubit) : Unit {
           if (desired != M(q1)) {
               X(q1);
           }
       }
   }
```

Bu işlem artık kubiti klasik bir duruma getirerek %100 `Zero` veya %100 `One` döndürmesi sağlanabilir.
`Zero` ve `One`, bir kubit ölçümünün mümkün olan iki sonucunu gösteren sabitlerdir.

`SetQubitState` işlemi kubiti ölçer. Kubit istediğimiz durumdaysa `SetQubitState` başka bir işlem gerçekleştirmez, değilse `X` işlemini çalıştırarak kubitin durumunu istediğimiz duruma getirebiliriz.

#### <a name="about-q-operations"></a>Q# işlemleri hakkında

Q# işlemi bir kuantum alt yordamıdır. Diğer bir deyişle, diğer hisse işleme çağrıları içeren çağrılabilir bir yordamdır.

İşlemin bağımsız değişkenleri parantez içinde tanımlama grubu olarak belirtilir.

Bir iki nokta işareti eklendikten sonra işlemin dönüş türü belirtilir. Bu örnekte `SetQubitState` işleminin dönüşü yoktur, dolayısıyla `Unit` döndürüyor olarak işaret edilir. Bu F# dilindeki `unit` öğesinin Q# eşdeğeridir, kabaca C# dilindeki `void` ve Python'daki boş bir tanımlama grubuyla (`Tuple[()]`) karşılaştırılabilir.

İlk Q# işleminizde iki kuantum işlemi kullandınız:

* [`M`](xref:microsoft.quantum.intrinsic.m)Qubit durumunu ölçen işlem
* [`X`](xref:microsoft.quantum.intrinsic.x)Bir qubit durumunu ters döndüren işlem

Kuantum işlemi, kubitin durumunu dönüştürür. Bazen kuantum işlemleri, klasik mantıksal geçitlere benzetildiğinden geçit olarak adlandırılır. Bu kullanım kuantum bilgisayarların ilk dönemlerine dayanır. Bu dönemde algoritmaların yalnızca teorik yapılardı ve klasik bilgi işlem devre şemalarına benzer şekilde görselleştirilirdi.

### <a name="counting-measurement-outcomes"></a>Ölçüm sonuçlarını sayma

Sonrasında `SetQubitState` işleminin etkisini göstermek için bir `TestBellState` işlemi eklenir. Bu işlem giriş olarak `Zero` veya `One` alır. Ardından `SetQubitState` işlemini bu girişle birkaç kez çağırıp kubitin ölçümünden döndürülen `Zero` sayısı ile döndürülen `One` sayısını hesaplar. Elbette bu ilk `TestBellState` işlemi simülasyonunda çıkışın parametre girişi `Zero` döndüreceğinden, tüm kubit ölçümlerinin `Zero` ile ayarlanmış olduğunu ve parametre girişi `One` döndüreceğinden tüm kubit ölçümlerinin `One` ile ayarlanmış olduğunu göstermesi beklenir. Ayrıca, `TestBellState` üst konumu ve entanglement 'i göstermek için öğesine kod ekleyeceğiz.

Aşağıdaki işlemi `Bell.qs` dosyasında ad alanının içine, `SetQubitState` işleminin sonuna ekleyin:

```qsharp
   operation TestBellState(count : Int, initial : Result) : (Int, Int) {

       mutable numOnes = 0;
       using (qubit = Qubit()) {

           for (test in 1..count) {
               SetQubitState(initial, qubit);
               let res = M(qubit);

               // Count the number of ones we saw:
               if (res == One) {
                   set numOnes += 1;
               }
           }
            
           SetQubitState(Zero, qubit);
       }

       // Return number of times we saw a |0> and number of times we saw a |1>
       Message("Test results (# of 0s, # of 1s): ");
       return (count - numOnes, numOnes);
   }
```
`return`( `Message` ) () [Microsoft. hisse. iç. ileti] işleviyle konsolda açıklayıcı bir ileti yazdırmak için önce bir satır ekledik.

Bu işlem (`TestBellState`) `count` yinelemeleri için döngü yapar, bir kubitte belirtilen `initial` değerini ayarlar ve ardından sonucu ölçer (`M`). Kaç sıfır ve bir ölçtüğümüzle ilgili istatistikleri toplar ve bunları çağrıyı yapana döndürür. Bir gerekli işlem daha gerçekleştirir. Kubiti döndürmeden önce bilinen bir duruma (`Zero`) sıfırlayarak diğerlerinin bu kubiti bilinen durumda ayırmasına olanak tanır. Bu, `using` deyimi için gereklidir.

#### <a name="about-variables-in-q"></a>Q içindeki değişkenler hakkında\#

Varsayılan olarak Q# dilinde değişkenler sabittir; bunların değeri bağlandıktan sonra değiştirilemez. Sabit bir değişkenin bağlamasını göstermek için `let` anahtar sözcüğü kullanılır. İşlem bağımsız değişkenleri her zaman sabittir.

Değeri değişebilen `numOnes` gibi bir değişkene ihtiyacınız varsa değişkeni `mutable` anahtar sözcüğüyle bildirebilirsiniz. Değişebilir değişkenin değeri `setQubitState` deyimi kullanılarak değiştirilebilir.

Her iki durumda da, değişkenin türü derleyici tarafından çıkarsanır. Q# dilinde değişkenler için herhangi bir türde ek açıklama gerekmez.

#### <a name="about-using-statements-in-q"></a>`using`Q içindeki deyimler hakkında\#

Q# dilinde `using` deyimi de özeldir. Kubitleri bir kod bloğunda kullanım amacıyla ayırmak için kullanılır. Q# dilinde tüm kubitler dinamik olarak ayrılır ve serbest bırakılır; karmaşık bir algoritmanın tüm yaşam süresi boyunca orada olan sabit kaynaklar değillerdir. Başlangıçta `using` deyimi bir kubit kümesi ayırır ve bloğun sonunda bu kubitleri serbest bırakır.

## <a name="execute-the-code-from-the-command-line"></a>Komut satırından kodu yürütün

Kodu çalıştırmak için, komutunu sağlamamız durumunda, çağrılabilir olarak çalıştırılabilir *olan* derleyiciyi belirtmemiz gerekir `dotnet run` . Bu, doğrudan çağrılabilir öğesinden bir satır eklenerek Q # dosyasında basit bir değişiklik ile yapılır `@EntryPoint()` : `TestBellState` Bu durumda işlem. Tam kod şu şekilde olmalıdır:

```qsharp
namespace Bell {
    open Microsoft.Quantum.Canon;
    open Microsoft.Quantum.Intrinsic;

    operation SetQubitState(desired : Result, target : Qubit) : Unit {
        if (desired != M(target)) {
            X(target);
        }
    }

    @EntryPoint()
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using (qubit = Qubit()) {

            for (test in 1..count) {
                SetQubitState(initial, qubit);
                let res = M(qubit);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, qubit);
        }

    // Return number of times we saw a |0> and number of times we saw a |1>
    Message("Test results (# of 0s, # of 1s): ");
    return (count - numOnes, numOnes);
    }
}
```

Programı çalıştırmak için `count` `initial` komut satırından ve bağımsız değişkenleri belirtmeniz gerekir. Örneğin `count = 1000` , ve ' i seçelim `initial = One` . Aşağıdaki komutu girin:

```dotnetcli
dotnet run --count 1000 --initial One
```

Aşağıdaki çıktıyı gözlemleymelisiniz:

```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

İle çalışırsanız şunu `initial = Zero` gözlemleyebilirsiniz:

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

## <a name="prepare-superposition"></a>Süper konumu hazırlama

Şimdi, s # ' ın üst konuma qubits 'i nasıl koyadığına bakalım.  Hatırlayacağınız gibi bir kubit 0 ve 1 süper konumlarında olabilir.  Bunu gerçekleştirmek için `Hadamard` işlemini kullanacağız. Kubitin klasik durumlardan birine olması halinde (ölçümün her zaman `Zero` veya her zaman `One` döndürmesi durumunda) `Hadamard` ya da `H` işlemi kubiti ölçümün %50 oranında `Zero` ve %50 oranında `One` döndüreceği bir duruma alır.  Kavramsal olarak kubitin `Zero` ile `One` arasındaki bir noktada olduğu düşünülebilir.  Şimdi `TestBellState` işleminin simülasyonunu yaptığımızda, ölçüm sonrasında elde edilen sonuçların `Zero` ve `One` için yaklaşık olarak eşit değerler verdiğini göreceğiz.  

### <a name="x-flips-qubit-state"></a>`X`qubit durumunu çevirir

İlk olarak kubiti çevirmeyi deneyeceğiz. (Kubit `Zero` durumundaysa `One` durumuna çevireceğiz veya aksi halde işlemin tam tersini yapacağız.) Bu, kubiti `TestBellState` işleminde ölçmeden önce bir `X` işlemi gerçekleştirilerek yapılır:

```qsharp
X(qubit);
let res = M(qubit);
```

Sonuçlar artık tersine çevrilir:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(1000, 0)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s):
(0, 1000)
```

Şimdi qubits 'in hisse özelliklerini keşfedelim.

### <a name="h-prepares-superposition"></a>`H`üst konumu hazırlar

Önceki çalıştırmadaki `X` işlemini bir `H` veya Hadamard işlemiyle değiştirmemiz yeterli olacaktır. Kubiti 0'dan 1'e kadar tümüyle çevirmek yerine yalnızca yarı yola kadar çevireceğiz. `TestBellState` işleminde değiştirilen satırlar şöyle görünür:

```qsharp
H(qubit);
let res = M(qubit);
```

Daha ilginç sonuçlar görülmeye başlar:

```dotnetcli
dotnet run --count 1000 --initial One
```

```output
Test results (# of 0s, # of 1s):
(496, 504)
```

```dotnetcli
dotnet run --count 1000 --initial Zero
```

```output
Test results (# of 0s, # of 1s):
(506, 494)
```

Her ölçtüğümüzde klasik bir değer bekleriz ama kubit 0 ile 1 arasında yarı yoldadır, dolayısıyla (istatistiksel olarak) ölçülerin yarısında 0 ve yarısında da 1 elde ederiz.
Bu **süper konum** olarak bilinir ve bize kuantum durumunun ilk gerçek görünümünü verir.

## <a name="prepare-entanglement"></a>Dolaşıklığı hazırlama

Şimdi Q# ile kubitleri dolaşık hale getirme işleminin nasıl ifade edildiğine bakalım.
İlk olarak kubiti başlangıç durumuna getireceğiz ve ardından `H` işlemini kullanarak süper konuma alacağız.  Ardından, ilk qubit 'i ölçüyoruz, `CNOT` denetlenen-Not için temsil eden yeni bir işlem () kullanıyoruz.  Bu işlemi yürütmenin iki kubit üzerindeki sonucu, birinci kubitin `One` olması durumunda ikinci kubiti çevirmektir.  Şimdi iki kubit de dolaşık hale geldi.  İlk kubit için istatistiklerimiz değişmemiştir (ölçüm sonrasında `Zero` veya `One` olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. `CNOT` geçidimiz iki kubiti dolaşık hale getirmiş, bu şekilde ilkine olanın aynısı diğerine de olmuştur. Ölçümleri ters çevirirseniz (ilk kubitten önce ikincisini yaparsanız), aynı durum ortaya çıkar. İlk ölçüm rastgele olacak ve ikincisi ilkinde bulunanla aynı yolu izleyecektir.

Yapacağımız ilk şey, bir yerine iki qubit ayırır `TestBellState` :

```qsharp
using ((q0, q1) = (Qubit(), Qubit())) {
```

Bu sayede `TestBellState` işleminde ölçüm yapmadan (`M`) önce yeni bir işlem (`CNOT`) ekleyebileceğiz:

```qsharp
SetQubitState(initial, q0);
SetQubitState(Zero, q1);

H(q0);
CNOT(q0, q1);
let res = M(q0);
```

İlk kubiti başlatarak, başladığımızda kubitin her zaman `Zero` durumunda olduğundan emin olmak için bir `SetQubitState` işlemi daha eklemiştik.

Serbest bırakmadan önce ikinci kubiti de sıfırlamamız gerekiyor.

```qsharp
SetQubitState(Zero, q0);
SetQubitState(Zero, q1);
```

Yordamın tamamı şimdi şöyle görünür:

```qsharp
    operation TestBellState(count : Int, initial : Result) : (Int, Int) {

        mutable numOnes = 0;
        using ((q0, q1) = (Qubit(), Qubit())) {
            for (test in 1..count) {
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

                H(q0);
                CNOT(q0,q1);
                let res = M(q0);

                // Count the number of ones we saw:
                if (res == One) {
                    set numOnes += 1;
                }
            }

            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
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
                SetQubitState(initial, q0);
                SetQubitState(Zero, q1);

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
            
            SetQubitState(Zero, q0);
            SetQubitState(Zero, q1);
        }

        // Return times we saw |0>, times we saw |1>, and times measurements agreed
        Message("Test results (# of 0s, # of 1s, # of agreements)");
        return (count-numOnes, numOnes, agree);
    }
```

Yeni dönüş değeri (`agree`), ilk kubitten gelen ölçümün ikinci kubitin ölçümüyle her eşleşmesinin kaydını tutar.

Elde ettiğimiz kodu çalıştırma:

```dotnetcli
dotnet run --count 1000 --initial One
```
```output
(505, 495, 1000)
```
```dotnetcli
dotnet run --count 1000 --initial Zero
```
```output
Test results (# of 0s, # of 1s, # of agreements)
(507, 493, 1000)
```

Genel bakışta belirtildiği üzere ilk kubit için istatistiklerimiz değişmemiştir (0 veya 1 olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. Bunun nedeni bu kubitlerin dolaşık olmasıdır!

## <a name="next-steps"></a>Sonraki adımlar

[Grover araması](xref:microsoft.quantum.quickstarts.search) başlıklı öğreticide kuantum bilişiminin en popüler algoritmalarından biri olan Grover aramasını oluşturup çalıştırma adımları gösterilir ve kuantum bilişimiyle gerçek sorunları çözmek için kullanılabilecek güzel bir Q# programı örneği sunulur.  

[Quantum Geliştirme Seti'ni Kullanmaya Başlama](xref:microsoft.quantum.welcome) sayfasında, Q# dilini ve kuantum programlamayı öğrenmek için başvurabileceğiniz diğer yöntemlerle ilgili öneriler sunulur.
