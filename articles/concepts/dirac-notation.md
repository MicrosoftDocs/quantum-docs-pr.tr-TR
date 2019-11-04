---
title: Dirac gösterimi | Microsoft Docs
description: Dirac gösterimi
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184772"
---
# <a name="dirac-notation"></a>Dirac gösterimi

Sütun vektör gösterimi doğrusal Alton içinde ikizde olduğunda, genellikle birden çok qubit ile ilgilenirken, daha fazla bilgi almak için daha fazla.  Örneğin, $ \psı $ öğesini bir vektör olacak şekilde tanımladığımızda, $ \psı $ ' ın bir satır veya bir sütun vektörü olduğunu açıkça temizlemez.  Bu nedenle, $ \phi $ ve $ \psı $ vektörse, $ \fi $ ve $ \psı $ şekilleri bağlamda anlaşılır olabileceğinden $ \phi \psı $ çiftse, eşit olarak belirsiz olur.  Vektörlerin şekilleriyle ilgili belirsizliğin ötesinde, daha önce sunulan doğrusal cebirsel gösterimini kullanan basit vektörleri ifade etmek çok daha kısacası olabilir. Örneğin, her bir qubitin $0 $ değerini aldığı bir $n $-qubit durumunu anlatmak istiyorsanız, durumu 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cnoktalar \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

Vektör, katlanarak büyük bir alanda bulunduğundan ve bu gösterim, önceki gösterim kullanılarak verilen durumun en iyi açıklaması olduğundan, bu Tensor ürününü değerlendiren bir kurs pratik değildir.  

[*Dirac gösterimi*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) bu sorunları, yeni bir dil sunarak hisse alanı tam ihtiyaçlarını karşılayacak şekilde çözer.  Bu nedenle, okuyucunun bu bölümdeki örnekleri, hisse durumlarının nasıl tanımlandığına ilişkin bir grup olarak bu bölümde yer alan örnekleri görüntüleyemeyeceğini, ancak okuyucuyu, Express hisse fikirlerini öz için kullanılabilecek öneriler olarak görüntülemesini öneririz.

Dirac gösteriminde iki tür vektör vardır: bir arada bir *örgü* veya iç ürün oluşturduklarında, adlandırılmış *bir vektör vektörü* ve *demet* vektörü.  $ \Psı $ bir sütun vektörü ise, $ \ket{\psı} $ olarak Dirac gösterimine yazarız; burada $ \ket{\cdot} $, bir birim sütunu vektörü, yani bir *demet* vektörü olduğunu gösterir.  Benzer şekilde, satır vektörü $ \psi ^ \gger $ $ \bra{\psı} $ olarak ifade edilir. Diğer bir deyişle, $ \psı ^ \hanger $, $ \ PSI $ ' ın devrik devriği için giriş odaklı karmaşık Birleşik uygulama uygulanarak elde edilir. Köşeli ayraç gösterimi doğrudan $ \braket{\psı | \psı} $ öğesinin tek bir vektörü olan vektör $ \psı $ 'ın iç ürünüdür ve bu, tanım $1 ' dir.  

Daha genel olarak, $ \psı $ ve $ \phi $, hisse matlılık vektörlerine sahip olduğu anlamına gelir. State $ \ket{\psı} $ $ \ket{\phi} $ $ | \braket{\phi | \psı} | ^ 2 $ şeklindedir.  

Aşağıdaki kural, sıfır ve bir (tek qubit hesaplama tabanlı durumlar) değerlerini kodlayan hisse durumlarının tanımlanmasında kullanılır:

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}, \qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \demet{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Örnek: Dirac gösterimi ile Hadamard işlemini temsil etme

Aşağıdaki gösterim genellikle, Hadamard kapısını $ \ket{0}$ ve $ \tus{1}$ ' a uygulamanın (Bloch Sphere ' de $ + x $ ve $-x $ yönlerine karşılık gelen birim vektörlerine karşılık gelen durumları) belirlemek için kullanılır:

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\demet{0} = \ket{+}, \qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\demet{1} = \tus{-}.
$$

Bu durumlar Ayrıca, $ \ket{0}$ ve $ \tus{1}$ toplamı olarak Dirac gösterimi kullanılarak da Genişletilebilir:

$ $ \ket{+} = \frac{1}{\sqrt{2}} (\ayraç{0} + \ayraç{1}), \qquad \demet{-} = \frac{1}{\sqrt{2}} (\tus{0}-\tus{1}).
$$

### <a name="computational-basis-vectors"></a>Hesaplama tabanlı vektörler
Bu durum, bu durumların neden genellikle *Hesaplama tabanlı*olarak çağrıldığını gösterir: her hisse maç durumu her zaman hesaplama tabanlı vektörlerin toplamı olarak ifade edilebilir ve bu tür toplamların adı, Dirac gösterimi kullanılarak kolayca ifade edilir  Aynı zamanda, $ \ket{+} $ ve $ \ket{-}$ için de aynı zamanda hisse Adaları için de bir temel oluşturacak şekilde listesiyse de geçerlidir.  Bunu şu şekilde görebilirsiniz:

$ $ \demet{0} = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}), \qquad \demet{1} = \frac{1}{\sqrt{2}} (\ket{+}-\tus{-}).
$$

Dirac gösterimine bir örnek olarak, $0 $ ve $1 $ arasındaki iç ürün olan braket $ \braket{0 | 1} $ öğesini düşünün.  Bu, şöyle yazılabilir 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ End {bmatrix} = 0. $ $

Bu, $ \ket{0}$ ve $ \demet{1}$ ' in dikey vektörleridir, yani $ \braket{0 | 1} = \braket{1 | 0} = $0.  Ayrıca, tanım $ \braket{0 | 0} = \braket{1 | 1} = 1 $, bu da iki hesaplama tabanlı vektörde *orthonormal*çağrılabilir.
Bu orthonormal özellikleri aşağıdaki örnekte yararlı olacaktır. $ \Ket{\psı} = {\frac{3}{5}} \tus{1} + {\frac{4}{5}} \tus{0}$, $ \braket{1 | 0} = $0, $1 $ ölçmeye olasılığı olduğunda  

$ $ \big | \braket{1 | \psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \ Right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>Tensor ürün gösterimi
Dirac gösterimi Ayrıca, içindeki örtük bir Tensor ürün yapısını da içerir.  Bu, hisse alma sırasında iki ilişkili hisse al kaydı tarafından tanımlanan eyalet vektörünün, iki durumlu vektörün tencursor ürünleri olduğundan önemlidir.  Bir hisse veya daha fazla öneme sahip olmak isterseniz, öz, Tensor ürün yapısını açıklayan veya önem taşıyan bir hesaplama açıklanmıştır.  Tensor ürün yapısı, her iki hisse alım vektörü $ \phi $ ve $ \psı $ $ \ket{\psı} \ket{\phi} $ olarak $ \psı \otimes \phi $ yazabildiğimiz anlamına gelir. bazen $ \ket{\psı} \otimes \ket{\phi} $ olarak açıkça yazılmış, ancak $ \otimes $ kuralına göre kurala göre vektörde bulunan vektörde gereksizdir.  Örneğin, sıfır duruma göre başlatılan iki qubits ile durum şu şekilde verilir

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \tus{0} \ otimes \ket{0}= \tus{0} \ayraç{0}.
$$

Benzer şekilde, $p $ tamsayısı için $ \ket{p} $ durumu, ikili gösterimde $p $ tamsayı olarak kodlayan bir hisse durumu temsil eder.  Örneğin, $5 $ sayısını işaretsiz bir ikili kodlama kullanarak ifade etmek istiyoruz.

$ $ \ket{1}\ayraç{0}\ayraç{1} = \demet{101} = \demet{5}.
$$

Bu gösterimde $ \ket{0}$ tek bir-qubit durumuna başvurmalıdır, ancak bunun yerine $0 $ öğesinin ikili kodlamasını depolayan bir *qubit kaydı* olmalıdır.  Bu iki gösterimdeki farklar genellikle bağlamdan net değildir.  Bu kural, aşağıdaki yollarla yazılıyolabilen ilk örneği basitleştirmek için yararlıdır:

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cnoktalar \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cnoktalar \otimes \demet{0}= | 0 \ cnoktalar 0 \ Rangle = \demet{0}^ {\otimes n} = \ demet{0}.
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Örnek: Dirac gösterimi ile süper konumu açıklama
Bir hisse yerini anlatmak için Dirac gösterimini nasıl kullanabileceğinizi gösteren başka bir örnek olarak, her bir olası bit $n dizesi için eşit üst konum olan bir hisse

$ $ H ^ {\otimes n} \demet{0} = \frac{1}{2 ^ {n/2}} \sum_{j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}.
$$

Burada, toplamın neden $0 $ ' den $2 ^ {n}-$1 ' e kadar $ bit $n olduğunu merak edebilirsiniz.  İlk olarak, $ bit $n $ bitler 'nin gerçekleştirebileceğine yönelik $2 ^ {n} $ farklı yapılandırma olduğunu unutmayın.  Bu, bir bitin $2 $ değer alıp belirleyebilmesini, ancak iki bitin $4 $ değer ve benzeri bir işlem yapabilmesi gerektiğini belirterek görebilirsiniz. Bu, genel olarak, $2 ^ n $ farklı olası bit dizeleri olduğu, ancak bunların hiçbirinde en büyük değer olan $1 \ cnoktalar 1 = 2 ^ n-$1 olduğu anlamına gelir ve bu nedenle toplamın üst sınırı budur.
Bu örnekte, bu notational kuralı her bir qubit için sıfıra başlatıldığından hesaplama bazlı durum için ayrıldığından, bu örnekte $ \ket{+} ^ {\otimes n} = \ket{+} $ öğesini benzerleme vurguladı to $ \ket{0}^ {\otimes n} = \tus{0}$ olarak kullandık.  Böyle bir kural bu durumda denenirken, hisse bilgi işlem belgelerinde işe alınamaz.

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac gösterimi ile doğrity belirtme
Daha iyi bir Dirac gösterimi özelliği, doğrusal olduğu olgusaldır.  Dört hisse alım durumu vektörü için yazmak istiyorsanız, 

$ $ (\Alpha \ket{\psı} + \beta\ket{\phi}) \otimes (\gama \ket{\chi} + \delta \ket{\omega}) = \harfler \ gama \ket{\psi}\ket{\chi} + \harflerden \delta \ket{\psi}\ket{\omega} + \beta\gamma\ket{\phi}\ket{\chi} + \beta\delta\ket{\phi}\ket{\omega}. $ $

Yani, durum vektörleri arasında tencursor ürünlerinin alınması normal çarpmaya benzer şekilde görünmesi için Dirac gösteriminde Tensor ürün gösterimini dağıtabilirsiniz.

Köşeli vektörler, demet vektörlerine benzer bir kural izler.  Örneğin, $ \bra{\psi}\bra{\phi} $ vektörü $ \psı ^ \hanger \otimes \phi ^ \dağılım = (\psı\otimes \fi) ^ \hanger $. Demet vektörü $ \ket{\psı} $ $ \Alpha \ket{0} + \ Beta \ demet{1}$ ise, vector öğesinin köşeli vektör sürümü $ \bra{\psı} = \ket{\psı} ^ \hanger = (\bra{0}\Alpha ^ * + \bra{1}\beta ^ *) $ şeklindedir.

Örnek olarak, durumları $ \ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \tus{0}$ ' nın $ \ket{+} $ veya $ \ demet olması için bir hisse kullanımı olduğunu varsayalım.{-}$. Daha sonra, cihazın durumun $ \demet{-}$ olduğunu gösteren bir olasılık 

$ $ | \braket{-| \psı} | ^ 2 = \left | \frac{1}{\sqrt{2}} (\bra{0}-\bra{1}) (\frac{3}{5} \ayraç{1} + \frac{4}{5} \ayraç{0}) \ Right | ^ 2 = \left |-\frac{3}{5 \ sqrt{2}} + \frac{4}{5 \ sqrt{2}} \ Right | ^ 2 = \frac{1}{50}. $ $

Negatif işaretin olasılık hesaplamasında görünmesi, hisse alma 'nın klasik bilgi işlem üzerinden daha fazla avantaj elde eden mekanizmalardan biridir.

## <a name="ketbra-or-outer-product"></a>ketya veya dış ürün
Dirac gösterimi ile tartışmak için en son öğe, *ketya* veya dış üründür.  Dış ürün, $ \ket{\psı} \bra{\phi} $ olarak Dirac gösterimlerine ve bazen Bras ve kets brakets olarak ters sırada gerçekleştiğinden, bazı durumlarda ketbras olarak adlandırılır.  Dış ürün, hisse ve ABD devleti $ \psı $ ve $ \fi $ için $ \ket{\psı} \bra{\phi} = \psı \ Fi ^ \gger $ olarak matris çarpma aracılığıyla tanımlanır.  Bu gösterimi en basit ve en sık kullanılan örnek,

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ End {bmatrix} \qquad \ demet{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ End {bmatrix}.
$$

Ketbras, her zaman sabit bir değere bir hisse durumu yansıdığından Projektör olarak adlandırılır.  Bu işlemler Unitary olmadığından (ve bir vektör 'nin norm de korumadığından), bir hisse bilgisayarının bir projektörün bir projektörü kesin bir şekilde uygulayamaması halinde gelmelidir.  Ancak, bir hisse başında ölçüm durumundaki eylemi açıklayan güzel bir iş vardır.  Örneğin, $ \ket{\psı} $ değerini $0 $ olarak ölçyoruz, bu durumda durum deneyimlerinin sonucu olarak ortaya çıkan dönüştürme

  $ $ \ket{\psi} \sağtarrow \frac{(\demet{0} \bra{0}) \ket{\psı}}{| \braket{0 | \psı} |} = \demet{0}, $ $

Bunlardan biri, durumu ölçmenizi ve $ \ket{0}$ olduğunu bulmanızı bekliyor.  Yeniden yinelemek için, bu tür projektörler bir hisse bir bilgisayardaki bir duruma göre belirlenebilir.  Bunun yerine, bazı sabit olasılığa sahip olan Result $ \ket{0}$ ile en iyi şekilde rastgele uygulanabilir.  Bu tür bir ölçünün başarılı olma olasılığı, devlet projektörün beklentisi değeri olarak yazılabilir

$ $ \bra{\psı} (\demet{0} \bra{0}) \ket{\psı} = | \braket{\psi | 0} | ^ 2, $ $

Bu, projektörlerin ölçüm sürecini ifade etmenin yeni bir yolunu sunışını gösterir.

Bunun yerine, Multi-qubit durumunun $1 $ olması için ilk qubit 'in ölçülmesini düşünmemiz durumunda, bu işlemi projektör ve Dirac gösterimini kullanarak kolayca de açıklayabilir:

$ $ P (\Text{First qubit = 1}) = \bra{\psi}\left (\tus{1}\bra{1}\otimes \ bolbitti ^ {\otimes n-1} \right) \ket{\psı}.
$$

Burada kimlik matrisi, şu şekilde Dirac gösteriminde kolayca yazılabilir

$ $ \ cıvadone = \demet{0} \bra{0}+ \ayraç{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \ End{bmatrix}.
$$

İki-qubit olduğu durumlarda, projektörün şu şekilde genişletilebileceği 

$ $ \demet{1} \bra{1} \otimes \ID = \ket{1}\bra{1} \otimes (\ayraç{0} \bra{0}+ \tus{1} \bra{1}) = \tus{10}\bra{10} + \tus{11}\bra{11}.
$$

Daha sonra bunun, sütun vektörü gösterimi kullanılarak multiqubit durumları için ölçüm likelihoods hakkındaki tartışmaya tutarlı olduğunu görebiliriz:

$ $ P (\Text{First qubit = 1}) = \psi ^ \dağılım (e\_{10}e\_{10}^ \dağılım + e\_{11}e\_{11}^ \dağılım) \psi = | e\_{10}^ \dağılım \ psi | ^ 2 + | e\_{11}^ \ dağılım \ PSI | ^ 2, $ $

Multi-qubit ölçüm tartışmayla eşleşir.  Ancak, bu sonucun Multi-qubit örneğine genelleştirmeye yönelik Genelleştirme, sütun vektörü gösteriminden daha basit olan Dirac gösterimi kullanılarak hızlı bir şekilde daha basittir ve önceki işleme tamamen eşdeğerdir.

## <a name="density-operators"></a>Yoğunluk işleçleri

Dirac gösterimini kullanarak hızlı bir şekilde başka bir yararlı operatör de *durum işleci*olarak da bilinen bir *yoğunluk işleçtir*.
Bir hisse durumu vektörünün Yoğunluk İşleci $ \rho = \ket{\psı} \bra{\psı} $ biçimini alır.
Durumu bir açıklama yerine matris olarak temsil eden bu kavram, genellikle yararlı olur, olasılık hesaplamalarını temsil etmek için kullanışlı bir yöntem sağlar ve ayrıca bir birinin hem istatistiksel olmayan belirsizlik hem de hisse ansız bir belirsizlik belirlemesine izin verir aynı formalısm içinde.
Vektörlerden farklı olarak genel hisse alım işleçleri, bazı hisse bilgi işlem alanlarında ve alanın temel bilgilerini anlamak için gerekli değildir.
İlgilendiğiniz okuyucu için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)' de sunulan başvuru defterlerinden birini okumanızı öneririz.

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>S # ağ geçidi dizileri hisse durumlarıyla eşdeğer
Aylık gösterimi ve Q # programlama dili hakkında en son bir nokta: Bu belgenin onkümesinde, hisse Eyaleti 'nin hisse bilgi işlem ortamında temel nesne olduğunu belirttik.  Daha sonra, soru-cevap durumu kavramı olmadığı için soru-cevap olarak gelebilir.  Bunun yerine, tüm durumlar yalnızca bunları hazırlamak için kullanılan işlemler tarafından açıklanmıştır.  Önceki örnek bunun mükemmel bir çizimidir.  Bir kayıttaki her hisse bit dizesi için Tekdüzen üst konumunu ifade etmek yerine, sonucu $H ^ {\otimes n} \tus{0}$ olarak temsil edebiliriz.  Bu durumun katlanarak daha kısa olan bu açıklaması yalnızca, bununla ilgili olarak neden olabilecek avantaja sahip olmakla kalmaz, Ayrıca öz, algoritmayı uygulamak için yazılım yığınında yayılması gereken işlemleri tanımlar.  Bu nedenle, Q #, hisse durumlarından değil, kapı dizilerini göstermek için tasarlanmıştır; Ancak, teorik düzeyinde iki perspektif eşdeğerdir.

