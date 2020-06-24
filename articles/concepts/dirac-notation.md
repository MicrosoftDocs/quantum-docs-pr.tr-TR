---
title: Dirac gösterimi
description: Hisse durumlarını göstermek ve hisse alma işlemlerinin benzetimini yapmak için Dirac gösterimini kullanma hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269515"
---
# <a name="dirac-notation"></a>Dirac gösterimi

Sütun vektör gösterimi doğrusal Alton içinde ikizde olduğunda, genellikle birden çok qubit ile ilgilenirken, daha fazla bilgi almak için daha fazla.  Örneğin, $ \psı 'yi bir vektör olarak tanımladığımızda, $ $ \psı $ 'nin bir satır veya bir sütun vektörü olup olmadığı açıkça net bir şekilde görünmez.  Bu nedenle, $ \phi $ ve $ \psı $ vektörse, $ $ \fi $ ve $ \psı şekilleri bağlamda belirsiz olabileceğinden, $ \phi \psı çiftse eşit değildir $ .  Vektörlerin şekilleriyle ilgili belirsizliğin ötesinde, daha önce sunulan doğrusal cebirsel gösterimini kullanan basit vektörleri ifade etmek çok daha kısacası olabilir. Örneğin, $ her bir qubitin $0 değerini aldığı $n-qubit durumunu anlatmak istiyorsanız, $ durumu 

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cnoktalar \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } . $$  

Vektör, katlanarak büyük bir alanda bulunduğundan ve bu gösterim, önceki gösterim kullanılarak verilen durumun en iyi açıklaması olduğundan, bu Tensor ürününü değerlendiren bir kurs pratik değildir.  

[*Dirac gösterimi*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) bu sorunları, yeni bir dil sunarak hisse alanı tam ihtiyaçlarını karşılayacak şekilde çözer.  Bu nedenle, okuyucunun bu bölümdeki örnekleri, hisse durumlarının nasıl tanımlandığına ilişkin bir grup olarak bu bölümde yer alan örnekleri görüntüleyemeyeceğini, ancak okuyucuyu, Express hisse fikirlerini öz için kullanılabilecek öneriler olarak görüntülemesini öneririz.

Dirac gösteriminde iki tür vektör vardır: bir arada bir *örgü* veya iç ürün oluşturduklarında, adlandırılmış *bir vektör vektörü* ve *demet* vektörü.  $ \Psı $ bir sütun vektörü ise, $ \ket { } { \ CDOT $ ' ın bir } birim sütunu vektörü olduğunu (yani, bir *demet* vektörü olduğunu) $ \Ket \ PSI $ olarak Dirac gösterimine yazarız.  Benzer şekilde, satır vektörü $ \psi ^ \dağılım, $ $ \bra { \ PSI $ olarak ifade edilir } . Diğer bir deyişle, $ \ PSI ^ \gesger, $ $ \ PSI öğesinin devrik öğesine giriş tabanlı karmaşık Birleşik bir uygulama uygulanarak elde edilir $ . Köşeli ayraç gösterimi doğrudan $ { \bratus\psı | \psı } $ 'ın $ , Açıklama $1 ile olan vector $ \psı 'in iç ürünüdür $ .  

Daha genel olarak, $ \psı $ ve $ \phi, $ hisse devlet vektörleridir. bu durum, $ \ket \ PSI $ değerini $ \ket \ Fi $ olarak hesaplama olasılığının $ \ ' $ { | } { } { } | \braket { \ Fi \ | PSI } | ^ 2 $ olduğunu belirten $ \bratus\phi \ PSI $ şeklindedir.  

Aşağıdaki kural, sıfır ve bir (tek qubit hesaplama tabanlı durumlar) değerlerini kodlayan hisse durumlarının tanımlanmasında kullanılır:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Örnek: Dirac gösterimi ile Hadamard işlemini temsil etme

Aşağıdaki gösterim genellikle, Hadamard kapısını $ \ket{0 } $ ve $ \ket{1 $ ' a uygulamanın } ( $ Bloch Sphere ' de $ + x ve $-x yönlerine karşılık gelen birim vektörlerine karşılık gelen durumları) belirlemek için kullanılır $ :

$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = { \tus-}.
$$

Bu durumlar Ayrıca, $ \ket{0 } $ ve $ \ket{1 $ toplamı olarak Dirac gösterimi kullanılarak da Genişletilebilir } :

$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad { \tus-} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).
$$

### <a name="computational-basis-vectors"></a>Hesaplama tabanlı vektörler
Bu durum, bu durumların neden genellikle *Hesaplama tabanlı*olarak çağrıldığını gösterir: her hisse maç durumu her zaman hesaplama tabanlı vektörlerin toplamı olarak ifade edilebilir ve bu tür toplamların adı, Dirac gösterimi kullanılarak kolayca ifade edilir  Aynı zamanda, $ \ket { +} $ ve $ { \tus-} $ durumları için de aynı zamanda hisse Adaları için de bir temel oluşturacak şekilde dönüştürüme de geçerlidir.  Bunu şu şekilde görebilirsiniz:

$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\demet { +}-\ demet { -}).
$$

Dirac gösterimine örnek olarak, } $0 ve $1 arasındaki iç ürün olan braket $ \braketi| 1 $ öğesini düşünün $ $ .  Bu, şöyle yazılabilir 

$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $

Bu, $ \ket{0 } $ ve $ \ket{1 } $ 'ın diksel vektörler olduğunu, yani $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ olduğunu söyler.  Ayrıca, tanım $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , bu da iki hesaplama tabanlı vektörde *orthonormal*çağrılabilir.
Bu orthonormal özellikleri aşağıdaki örnekte yararlı olacaktır. Bir State $ \ket { \psı } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $ olduğunda, $ \braket{1 | 0 } = 0 $ ölçmenin olasılığı $1 $  

$ $ \ Big | \braket{1 | \psı } \ Big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \ Right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>Tensor ürün gösterimi
Dirac gösterimi Ayrıca, içindeki örtük bir Tensor ürün yapısını da içerir.  Bu, hisse alma sırasında iki ilişkili hisse al kaydı tarafından tanımlanan eyalet vektörünün, iki durumlu vektörün tencursor ürünleri olduğundan önemlidir.  Bir hisse veya daha fazla öneme sahip olmak isterseniz, öz, Tensor ürün yapısını açıklayan veya önem taşıyan bir hesaplama açıklanmıştır.  Tensor ürün yapısı, $ her iki hisse madevlet vektörü $ \phi $ ve $ \psi $ \ket \ PSI $ { } \ket \ { Fi } $, bazen açıkça $ \ket \ { PSI } \otimes \ket $ olarak yazılmış, { } ancak vektörlerin arasında $ \osüreler yazmak $ için $  Örneğin, sıfır duruma göre başlatılan iki qubits ile durum şu şekilde verilir

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } = \begin{1 0 \end{ bmatrix } \\ \\ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .
$$

Benzer şekilde, tam sayı için $ \ket{p } $ durum $p, $ tam sayı $p bir ikili gösterimde kodlayan bir hisse durumu temsil eder $ .  Örneğin, $5 sayısını $ işaretsiz bir ikili kodlama kullanarak ifade etmek istiyoruz.

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

Bu gösterimde $ \ket{0 } $ bir tek qubit duruma başvurmalıdır, ancak bunun yerine $0 ikili kodlamasını depolayan bir *qubit kaydı* vardır $ .  Bu iki gösterimdeki farklar genellikle bağlamdan net değildir.  Bu kural, aşağıdaki yollarla yazılıyolabilen ilk örneği basitleştirmek için yararlıdır:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cnoktalar \otimes \begin { bmatrix } 1 \\ \\ 0 \ End{ bmatrix } = \ket{0 } \otimes \cnoktalar \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Örnek: Dirac gösterimi ile süper konumu açıklama
Bir hisse düzeyini anlatmak için Dirac gösterimini nasıl kullanabileceğinizi gösteren başka bir örnek olarak, her bir olası bit dizesi için eşit bir süper konum olan hisse bir durum yazmak için aşağıdaki eşdeğer yöntemleri göz önünde bulundurun $n$

$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = { \tus+} ^ {\otimes n } .
$$

Burada toplamın neden $0 ' den $ $2 ^ {n-1 ' e kadar } $ $n bitler 'e geçgireceğini merak edebilirsiniz $ .  İlk olarak, } $n bitlerin gerçekleştirebileceğine ilişkin $2 ^ {n $ farklı yapılandırma olduğunu unutmayın $ .  Bu, bir bitin $2 $ değer alıp belirleyebilmesini, ancak iki bitin $4 değer alıp bu şekilde devam edebilir olduğunu belirterek görebilirsiniz $ . Bu, genel olarak, $2 ^ n $ farklı olası bit dizelerinin olduğu, ancak bunların hiçbirinde kodlandığı en büyük değerin $1 \cdots 1 = 2 ^ n-1 olduğu anlamına gelir $ ve bu nedenle toplamın üst sınırı budur.
Yan bir not olarak, bu { } { } } } notational kuralı genellikle her bir qubit, sıfıra başlatıldığından hesaplama tabanlı durum için ayrıldığından, bu örnekte $ \ket +} ^ {\otimes n = \ket +} $, benzerleme vurguladı ile $ \ket{0 ^ {\otimes n = \ket{0 $ kullandık.  Böyle bir kural bu durumda denenirken, hisse bilgi işlem belgelerinde işe alınamaz.

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac gösterimi ile doğrity belirtme
Daha iyi bir Dirac gösterimi özelliği, doğrusal olduğu olgusaldır.  Dört hisse alım durumu vektörü için yazmak istiyorsanız, 

$ $ (\Alpha \ ayraç { \ psi } + \beta \ket { \fi } ) \otimes (\gama \ ayraç { \ çi } + \delta \ayraç \ { Omega } ) = \alfa \gamma \ ayraç { \ PSI \ } ayraç \ { çi } + \alfa \delta \ { } { } \gamma \ket { } { } \delta \ket { } { } [\

Yani, durum vektörleri arasında tencursor ürünlerinin alınması normal çarpmaya benzer şekilde görünmesi için Dirac gösteriminde Tensor ürün gösterimini dağıtabilirsiniz.

Köşeli vektörler, demet vektörlerine benzer bir kural izler.  Örneğin, $ \bra { \ PSI } \bra { \phi } $ vektörü $ \psi ^ \gesger \otimes \phi ^ \hanger = (\psı \otimes \fi) ^ \hanger olan vector $ . Demet vektörü $ { \tus\psı $, } $ \Alpha \ket{0 } + \beta \ket{1 $ ise } Vector öğesinin köşeli vektör sürümü $ \bra { \ PSI } = \tus\psı { } ^ \gger = (\bra{0 } \Alpha ^ * + \bra{1 } \beta ^ *) $ şeklindedir.

Örnek olarak, $ { \tus\psı } = \frac{3 } {5 } \ket{1 } + \frac{4 {5 \ket{0 } $ durumunun } } $ \ket { +} $ veya $ \tus-} $ olduğunu ölçmek için bir hisse öğesi kullanarak { $ Daha sonra, cihazın durumun $ \ket-} $ olduğunu belirten bir olasılık { 

$ $ | { \bratus-| \psı } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \ doğru | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \ Right | ^ 2 = \frac{1 } {50 } . $ $

Negatif işaretin olasılık hesaplamasında görünmesi, hisse alma 'nın klasik bilgi işlem üzerinden daha fazla avantaj elde eden mekanizmalardan biridir.

## <a name="ketbra-or-outer-product"></a>ketya veya dış ürün
Dirac gösterimi ile tartışmak için en son öğe, *ketya* veya dış üründür.  Dış ürün, $ { \tus\psı \bra \phi $ olarak Dirac gösterimler içinde temsil edilir } { } ve bazen Bras ve kets, brakets olarak ters sırada gerçekleştiğinden, bazı durumlarda ketbras olarak adlandırılır.  Dış ürün, t\ket { \ PSI } \bra { \phi } = \psı \ Fi ^ \linger $ $ \psi $ ve $ \fi $ olarak matris çarpma aracılığıyla tanımlanır.  Bu gösterimi en basit ve en sık kullanılan örnek,

$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \ qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{} 0 bmatrix&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} .
$$

Ketbras, her zaman sabit bir değere bir hisse durumu yansıdığından Projektör olarak adlandırılır.  Bu işlemler Unitary olmadığından (ve bir vektör 'nin norm de korumadığından), bir hisse bilgisayarının bir projektörün bir projektörü kesin bir şekilde uygulayamaması halinde gelmelidir.  Ancak, bir hisse başında ölçüm durumundaki eylemi açıklayan güzel bir iş vardır.  Örneğin, $ \ket \ PSI $ değerini $0 olarak ölçyoruz, { } $ Bu durumda durum deneyimlerinin bir sonucu olarak ortaya çıkan dönüşümdür

  $ $ \ demet { \ PSI } \sağtarrow \frac { (\ket{0 } \bra{0 } ) \demet { \ PSI } } {| \braket{0 | \psı } |} = \ket{0 } , $ $

Bunlardan biri, durumu ölçmenizi ve $ \ket{0 $ olacak şekilde bulmayı bekler } .  Yeniden yinelemek için, bu tür projektörler bir hisse bir bilgisayardaki bir duruma göre belirlenebilir.  Bunun yerine, } bazı sabit olasılığa sahip $ \ket{0 $ sonucu ile en iyi şekilde rastgele uygulanabilir.  Bu tür bir ölçünün başarılı olma olasılığı, devlet projektörün beklentisi değeri olarak yazılabilir

$ $ \bra { \ PSI } (\ket{0 } \bra{0 } ) \ayraç { \ PSI } = | \bratus\psi { | 0 } | ^ 2, $ $

Bu, projektörlerin ölçüm sürecini ifade etmenin yeni bir yolunu sunışını gösterir.

Bunun yerine, Multi-qubit durumunun $1 olması için ilk qubit 'in ölçülmesini düşünmemiz durumunda, $ Bu işlemi projektör ve Dirac gösterimini kullanarak kolayca de açıklayabilir:

$ $ P (\Text{First qubit = 1 } ) = \bra { \ PSI } \left (\ket{1 } \bra{1 } \otimes \cıvabitti ^ {\otimes n-1 } \ right) { \tus\psi } .
$$

Burada kimlik matrisi, şu şekilde Dirac gösteriminde kolayca yazılabilir

$ $ \ cıvadone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \ End{ bmatrix } .
$$

İki-qubit olduğu durumlarda, projektörün şu şekilde genişletilebileceği 

$ $ \ket{1 } \bra{1 } \otimes \ID = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .
$$

Daha sonra bunun, sütun vektörü gösterimi kullanılarak multiqubit durumları için ölçüm likelihoods hakkındaki tartışmaya tutarlı olduğunu görebiliriz:

$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dağılım (e e \_ {10} \_ {10 ^ \dağılım } + e e \_ {11} \_ {11 } ^ \dağılım) \psı = | e \_ {10 } ^ \ dağılım \ PSI | ^ 2 + | e \_ {11 } ^ \dağılım \psı | ^ 2, $ $

Multi-qubit ölçüm tartışmayla eşleşir.  Ancak, bu sonucun Multi-qubit örneğine genelleştirmeye yönelik Genelleştirme, sütun vektörü gösteriminden daha basit olan Dirac gösterimi kullanılarak hızlı bir şekilde daha basittir ve önceki işleme tamamen eşdeğerdir.

## <a name="density-operators"></a>Yoğunluk işleçleri

Dirac gösterimini kullanarak hızlı bir şekilde başka bir yararlı operatör de *durum işleci*olarak da bilinen bir *yoğunluk işleçtir*.
Hisse bir ABD devleti için bir yoğunluk işleci $ \rho = { \tus\psı } \bra { \ PSI $ biçimini alır } .
Durumu bir açıklama yerine matris olarak temsil eden bu kavram, genellikle yararlı olur, çünkü olasılık hesaplamalarını temsil etmek için kullanışlı bir yöntem sunar ve ayrıca bir birinin aynı formalronizde aynı şekilde hem istatistiksel olmayan belirsizlik hem de aynı şekilde, aynı şekilde, aynı şekilde, hem istatistiksel unilkliği hem de
Vektörlerden farklı olarak genel hisse alım işleçleri, bazı hisse bilgi işlem alanlarında ve alanın temel bilgilerini anlamak için gerekli değildir.
İlgilendiğiniz okuyucu için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)' de sunulan başvuru defterlerinden birini okumanızı öneririz.

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>S # ağ geçidi dizileri hisse durumlarıyla eşdeğer
Aylık gösterimi ve Q # programlama dili hakkında en son bir nokta: Bu belgenin onkümesinde, hisse Eyaleti 'nin hisse bilgi işlem ortamında temel nesne olduğunu belirttik.  Daha sonra, soru-cevap durumu kavramı olmadığı için soru-cevap olarak gelebilir.  Bunun yerine, tüm durumlar yalnızca bunları hazırlamak için kullanılan işlemler tarafından açıklanmıştır.  Önceki örnek bunun mükemmel bir çizimidir.  Bir kayıttaki her hisse bit dizesinde Tekdüzen üst konumunu ifade etmek yerine, sonucu $H ^ {\otimes n } \ket{0 $ olarak temsil edebiliriz } .  Bu durumun katlanarak daha kısa olan bu açıklaması yalnızca, bununla ilgili olarak neden olabilecek avantaja sahip olmakla kalmaz, Ayrıca öz, algoritmayı uygulamak için yazılım yığınında yayılması gereken işlemleri tanımlar.  Bu nedenle, Q #, hisse durumlarından değil, kapı dizilerini göstermek için tasarlanmıştır; Ancak, teorik düzeyinde iki perspektif eşdeğerdir.
