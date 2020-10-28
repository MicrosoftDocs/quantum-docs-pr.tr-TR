---
title: Entanglement 'i ile keşfet Q#
description: "' De bir hisse programı yazmayı öğrenin Q# . Quantum Development Kit'i (QDK) kullanarak Bell Durumu uygulaması geliştirme"
author: geduardo
ms.author: v-edsanc
ms.date: 05/29/2020
ms.topic: tutorial
uid: microsoft.quantum.write-program
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a1a49e18ac9330ca6e3cc89b3e58c96eccb91db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691663"
---
# <a name="tutorial-explore-entanglement-with-q"></a>Öğretici: Q\# ile dolaşıklığı keşfetme

Bu öğreticide, Q# qubits 'i işleyen ve ölçtüğünden ve üst konum ve entanglement 'in etkilerini gösteren bir programı nasıl yazacağınız gösterilmektedir.

Kuantum dolaşıklığı göstermek için Bell adında bir uygulama yazacaksınız.
Bell adı, en basit süper konum ve kuantum dolaşıklığı örneklerini göstermek için kullanılan iki kubitin belirli kuantum durumları olan Bell durumlarını ifade eder.

## <a name="pre-requisites"></a>Ön koşullar

Kodlamaya başlamaya hazırsanız devam etmeden önce şu adımları izleyin: 

* [Install](xref:microsoft.quantum.install) Tercih ettiğiniz dil ve geliştirme ortamınızı kullanarak hisse geliştirme setini kullanın.
* Makinenizde QDK zaten yüklüyse en son sürüme [güncelleştirdiğinizden](xref:microsoft.quantum.update) emin olun

Ayrıca, QDK 'yi yüklemeden anlatıcı olarak, programlama dilinin genel bakışlarını Q# ve hisse bilgi işlem kavramlarının ilk kavramlarını gözden geçirerek da izleyebilirsiniz.

## <a name="in-this-tutorial-youll-learn-how-to"></a>Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

> [!div class="checklist"]
> * Q 'da işlem oluşturma ve birleştirme\#
> * Qubits 'i üst konuma yerleştirmek için işlemler oluşturun, bunları zenginedin ve ölçün.
> * Bir benzeticide çalıştırılan bir programla hisse entanglement 'i gösterir Q# . 

## <a name="demonstrating-qubit-behavior-with-the-qdk"></a>QDK ile qubit davranışı gösterme

Klasik bitler 0 veya 1 gibi tek bir ikili değeri barındırırken, [kubitin](xref:microsoft.quantum.glossary#qubit) durumu 0 ve 1’in bir **süper konumunda** olabilir.  Kavramsal olarak, bir qubit durumu soyut bir alanda (vektör olarak da bilinir) bir yön olarak düşünülebilir.  Bir qubit durumu olası yönlere ait olabilir. İki **klasik durum** , iki yöndür. Bu da %100 oranında 0 ölçme şansını ve %100 oranında 1 ölçme şansını gösterir.

Ölçüm işlemi ikili sonuç üretir ve bir kubit durumunu değiştirir.
Ölçüm, 0 veya 1 olan bir ikili değer üretir.  Kubit, süper konumdan (herhangi bir yöne) klasik durumlardan birine geçer.  Bundan sonra aynı ölçümün başka bir işlemle müdahale edilmeden yinelenmesi durumunda aynı ikili sonuç ortaya çıkar.  

Birden çok kubit [**dolaşık hale getirilebilir**](xref:microsoft.quantum.glossary#entanglement).  Dolaşık bir kubitin ölçümünü yaptığınızda, diğerinin durumuna ilişkin bilginiz de güncelleştirilir.

Şimdi bu davranışın nasıl ifade ettireceğiz gösterilmektedir Q# .  Mümkün olan en basit programla başlayıp kuantum süper konumu ile kuantum dolaşıklığını göstermek için bunu geliştirirsiniz.

## <a name="creating-a-no-locq-project"></a>Proje oluşturma Q#

Yapmanız gereken ilk şey yeni bir Q# Proje oluşturmaktır. Bu öğreticide, [ Q# vs Code olan uygulamalara](xref:microsoft.quantum.install.standalone)göre ortamı kullanacağız.

Yeni bir proje oluşturmak için VS Code: 

1. **Görünüm** -> **Komut Paleti** ’ne tıklayın ve **Q#: Yeni Proje Oluştur** ’u seçin.
2. **Bağımsız konsol uygulaması** ’na tıklayın.
3. Projenin kaydedileceği konuma gidin ve **Proje Oluştur** ’a tıklayın.
4. Proje başarıyla oluşturulduğunda, sağ alt kısımdaki **Yeni proje aç...** seçeneğine tıklayın.

Bu durumda proje çağırılır `Bell` . Bu iki dosya oluşturur: `Bell.csproj` , proje dosyası ve `Program.qs` Q# uygulamamızı yazmak için kullandığımız bir uygulamanın şablonu. İçeriği şu `Program.qs` olmalıdır:

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
 
Bizim amamız, belirli bir hisse durumunda iki qubit hazırlanmaktır. Bu durumda, Q# eyaletlerin durumunu değiştirmek ve üst konum ve entanglement 'in etkilerini göstermek için ile qubit üzerinde nasıl çalışılacağı gösterilmektedir. Bu parçaları, qubit durumları, işlemleri ve ölçümü tanıtmak için bir parça oluşturacak şekilde oluşturacağız.

### <a name="initialize-qubit-using-measurement"></a>Ölçüyü kullanarak qubit Başlat

Aşağıdaki ilk kod parçacığında ' de qubits ile nasıl çalışacağız gösterilmektedir Q# .  İki işlem tanıtıyoruz [`M`](xref:Microsoft.Quantum.Intrinsic.m) ve [`X`](xref:Microsoft.Quantum.Intrinsic.X) bir qubit durumunu dönüştürecek. Bu kod parçacığında parametre olarak bir kubit ile kubitin içinde bulunmasını istediğimiz durumu temsil eden `desired` parametresini alan `SetQubitState` işlemi tanımlanmıştır.  `SetQubitState` işlemi, `M` işlemini kullanarak kubit üzerinde bir ölçüm gerçekleştirir.  Q#' De, bir qubit ölçümü her zaman `Zero` ya da döndürür `One` .  Ölçüm, istenen değere eşit olmayan bir değer döndürürse, `SetQubitState` "qubit" değerini çevirir; diğer bir deyişle, bir işlem çalıştırır ve bu, `X` qubit durumunu döndürülen ve geri çevrilen bir ölçünün olasılıkların ne olduğu yeni bir duruma geçirir `Zero` `One` . Bu şekilde, `SetQubitState` her zaman hedef qubit 'i istenen duruma geçirir.

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

`SetQubitState` işlemi kubiti ölçer. Qubit, istediğimiz durumdaysa, `SetQubitState` bunu tek başına bırakır; Aksi takdirde, `X` işlemi çalıştırarak qubit durumunu istenen duruma göre değiştirirsiniz.

#### <a name="about-no-locq-operations"></a>Q#İşlemler hakkında

Q#İşlem bir hisse alt yordamı. Diğer bir deyişle, diğer hisse işleme çağrıları içeren çağrılabilir bir yordamdır.

İşlemin bağımsız değişkenleri parantez içinde tanımlama grubu olarak belirtilir.

Bir iki nokta işareti eklendikten sonra işlemin dönüş türü belirtilir. Bu durumda, `SetQubitState` işlemin dönüş türü yoktur, bu nedenle döndürülen olarak işaretlenir `Unit` . Bu, Q# C# ' de `unit` kabaca benzer olan `void` ve Python 'da boş bir tanımlama grubu olan ( `()` tür Ipucuyla temsil edilen) F # ' ın eşdeğeridir `Tuple[()]` .

İlk işlem sırasında iki hisse işlem kullandınız Q# :

* [`M`](xref:Microsoft.Quantum.Intrinsic.m)Qubit durumunu ölçen işlem
* [`X`](xref:Microsoft.Quantum.Intrinsic.X)Bir qubit durumunu ters döndüren işlem

Kuantum işlemi, kubitin durumunu dönüştürür. Bazen kuantum işlemleri, klasik mantıksal geçitlere benzetildiğinden geçit olarak adlandırılır. Bu kullanım kuantum bilgisayarların ilk dönemlerine dayanır. Bu dönemde algoritmaların yalnızca teorik yapılardı ve klasik bilgi işlem devre şemalarına benzer şekilde görselleştirilirdi.

### <a name="counting-measurement-outcomes"></a>Ölçüm sonuçlarını sayma

Sonrasında `SetQubitState` işleminin etkisini göstermek için bir `TestBellState` işlemi eklenir. Bu işlem giriş olarak `Zero` veya `One` alır. Ardından `SetQubitState` işlemini bu girişle birkaç kez çağırıp kubitin ölçümünden döndürülen `Zero` sayısı ile döndürülen `One` sayısını hesaplar. Elbette bu ilk `TestBellState` işlemi simülasyonunda çıkışın parametre girişi `Zero` döndüreceğinden, tüm kubit ölçümlerinin `Zero` ile ayarlanmış olduğunu ve parametre girişi `One` döndüreceğinden tüm kubit ölçümlerinin `One` ile ayarlanmış olduğunu göstermesi beklenir. Ayrıca, `TestBellState` üst konumu ve entanglement 'i göstermek için öğesine kod ekleyeceğiz.

Aşağıdaki işlemi `Program.qs` dosyasında ad alanının içine, `SetQubitState` işleminin sonuna ekleyin:

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

Varsayılan olarak, ' deki değişkenler Q# sabittir; bu değerler bağlandıktan sonra değiştirilemez. Sabit bir değişkenin bağlamasını göstermek için `let` anahtar sözcüğü kullanılır. İşlem bağımsız değişkenleri her zaman sabittir.

Değeri değişebilen `numOnes` gibi bir değişkene ihtiyacınız varsa değişkeni `mutable` anahtar sözcüğüyle bildirebilirsiniz. Değişebilir değişkenin değeri `set` deyimi kullanılarak değiştirilebilir.

Her iki durumda da, değişkenin türü derleyici tarafından çıkarsanır. Q# değişkenler için herhangi bir tür ek açıklaması gerektirmez.

#### <a name="about-using-statements-in-q"></a>`using`Q içindeki deyimler hakkında\#

`using`İfade için de özeldir Q# . Kubitleri bir kod bloğunda kullanım amacıyla ayırmak için kullanılır. ' De Q# , tüm qubits, karmaşık bir algoritmanın tüm kullanım ömrü boyunca yer alan sabit kaynaklar yerine dinamik olarak ayrılır ve serbest bırakılır. Başlangıçta `using` deyimi bir kubit kümesi ayırır ve bloğun sonunda bu kubitleri serbest bırakır.

## <a name="run-the-code-from-the-command-prompt"></a>Komut isteminden kodu çalıştırma

Kodu çalıştırmak için, komut sağlamamız durumunda *, derleyicinin çalıştırılabilir olduğunu* söylememiz gerekir `dotnet run` . Bu, Q# `@EntryPoint()` çağrılabilir: `TestBellState` Bu durumda işlem tarafından doğrudan bir satır eklenerek, dosyada basit bir değişiklik ile yapılır. Tam kod şu şekilde olmalıdır:

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

Programı çalıştırmak için `count` `initial` komut isteminden ve bağımsız değişkenleri belirtmemiz gerekir. Örneğin `count = 1000` , ve ' i seçelim `initial = One` . Aşağıdaki komutu girin:

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

Şimdi Q# de bilgeler 'yi üst konuma yerleştirmek için nasıl ifade etmenin nasıl olduğunu inceleyelim.  Hatırlayacağınız gibi bir kubit 0 ve 1 süper konumlarında olabilir.  Bunu gerçekleştirmek için `Hadamard` işlemini kullanacağız. Kubitin klasik durumlardan birine olması halinde (ölçümün her zaman `Zero` veya her zaman `One` döndürmesi durumunda) `Hadamard` ya da `H` işlemi kubiti ölçümün %50 oranında `Zero` ve %50 oranında `One` döndüreceği bir duruma alır.  Kavramsal olarak kubitin `Zero` ile `One` arasındaki bir noktada olduğu düşünülebilir.  Şimdi `TestBellState` işleminin simülasyonunu yaptığımızda, ölçüm sonrasında elde edilen sonuçların `Zero` ve `One` için yaklaşık olarak eşit değerler verdiğini göreceğiz.  

### <a name="x-flips-qubit-state"></a>`X` qubit durumunu çevirir

İlk olarak, qubit 'i (qubit durumunda ise bunun tersi) ters çevirmeyi deneyeceğiz `Zero` `One` . Bu, kubiti `TestBellState` işleminde ölçmeden önce bir `X` işlemi gerçekleştirilerek yapılır:

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

### <a name="h-prepares-superposition"></a>`H` üst konumu hazırlar

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

Şimdi de Q# qubits 'e nasıl ifade vertığınızın yollarını inceleyelim.
İlk olarak kubiti başlangıç durumuna getireceğiz ve ardından `H` işlemini kullanarak süper konuma alacağız.  Ardından, ilk qubit 'i ölçüyoruz, `CNOT` *denetlenen-Not* için temsil eden yeni bir işlem () kullanıyoruz.  Bu işlemi iki qubit üzerinde çalıştırmanın sonucu, birinci qubit ise ikinci qubit 'i çevirmenize neden olur `One` .  Şimdi iki kubit de dolaşık hale geldi.  İlk kubit için istatistiklerimiz değişmemiştir (ölçüm sonrasında `Zero` veya `One` olma olasılığı %50’dir) ama şimdi ikinci kubiti ölçtüğümüzde ilk kubitte ölçülenle __her zaman__ aynı olduğu görülür. `CNOT` geçidimiz iki kubiti dolaşık hale getirmiş, bu şekilde ilkine olanın aynısı diğerine de olmuştur. Ölçümleri ters çevirirseniz (ilk kubitten önce ikincisini yaparsanız), aynı durum ortaya çıkar. İlk ölçüm rastgele olacak ve ikincisi ilkinde bulunanla aynı yolu izleyecektir.

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

Öğretici [Grover](xref:microsoft.quantum.quickstarts.search) araması, en popüler hisse alım algoritmalarından biri olan Grover araması oluşturma ve çalıştırma hakkında bilgi sağlar ve Q# Bu programın, hisse bilgi işlem ile gerçek sorunları çözümlemek için kullanılabilecek iyi bir örnek sunmaktadır.  

[Hisse geliştirme kiti Ile çalışmaya başlamak,](xref:microsoft.quantum.welcome) daha fazla bilgi edinmek ve bu programlama için daha fazla yol önerir Q# .
