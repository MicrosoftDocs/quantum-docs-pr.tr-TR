---
title: Dirac gösterimi açıklaması: hisse durumlarını göstermek ve hisse alma işlemlerinin benzetimini yapmak için Dirac gösterimini kullanma hakkında bilgi edinin.
Yazar: miktar Tumwriter uid: Microsoft. hisse. Concepts. Dirac MS. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: kavramsal No-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="dirac-notation"></a>Dirac gösterimi

Sütun vektör gösterimi doğrusal Alton içinde ikizde olduğunda, genellikle birden çok qubit ile ilgilenirken, daha fazla bilgi almak için daha fazla.  Örneğin, bir vektör olacak şekilde tanımladığımızda, $ \psi $ $ \psi $ bir satır veya bir sütun vektörü olup olmadığı açıkça net bir şekilde görünmez.  Bu nedenle, $ \phi $ ve $ \psi $ $ \phi \psi $ vektörseler bile, $ \phi $ ve şekilleri $ \psi $ bağlamda anlaşılır bir şekilde tanımlanabileceğinden, eşit olarak tanımlıysa, eşit olarak belirsiz olur.  Vektörlerin şekilleriyle ilgili belirsizliğin ötesinde, daha önce sunulan doğrusal cebirsel gösterimini kullanan basit vektörleri ifade etmek çok daha kısacası olabilir. Örneğin, $ $ her bir qubitin 0 değerini aldığı bir n-qubit durumunu anlatmak isterseniz, $ $ durumu 

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} . $$  

Vektör, katlanarak büyük bir alanda bulunduğundan ve bu gösterim, önceki gösterim kullanılarak verilen durumun en iyi açıklaması olduğundan, bu Tensor ürününü değerlendiren bir kurs pratik değildir.  

[*Dirac gösterimi*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) bu sorunları, yeni bir dil sunarak hisse alanı tam ihtiyaçlarını karşılayacak şekilde çözer.  Bu nedenle, okuyucunun bu bölümdeki örnekleri, hisse durumlarının nasıl tanımlandığına ilişkin bir grup olarak bu bölümde yer alan örnekleri görüntüleyemeyeceğini, ancak okuyucuyu, Express hisse fikirlerini öz için kullanılabilecek öneriler olarak görüntülemesini öneririz.

Dirac gösteriminde iki tür vektör vardır: bir arada bir *örgü* veya iç ürün oluşturduklarında, adlandırılmış *bir vektör vektörü* ve *demet* vektörü.  $ \psi $ Bir sütun vektörüdür, bu durumda $ \ket { \psi } $ $ \ket { \cdot ' ın bir } $ birim sütunu vektörü olduğunu, yani bir *demet* vektörü olduğunu gösterir.  Benzer şekilde, satır vektörü $ \psi ^ \dagger $ olarak ifade edilir $ \bra { \psi } $ . Diğer bir deyişle, ' ın $ \psi ^ \dagger $ devrime öğelerine giriş Wise karmaşık bir uygulama uygulanarak elde edilir $ \psi $ . Köşeli ayraç gösterimi, bu, $ \braket { \psi | \psi } $ $ \psi $ tanım 1 ' in kendisi ile vektör 'nin dahili çarpımı $ $ olduğunu doğrudan gösterir.  

Daha genel olarak, $ \psi $ ve $ \phi $ hisse ölçü eyalet vektörlerine sahip olmak, $ \braket { \phi | \psi } $ durumu %2 olarak ölçeceği anlamına gelir $ \ket { \psi } $ $ \ket { \phi } $ $ | \braket { \phi | \psi } | $ .  

Aşağıdaki kural, sıfır ve bir (tek qubit hesaplama tabanlı durumlar) değerlerini kodlayan hisse durumlarının tanımlanmasında kullanılır:

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket { 0 } ,\qquad
\begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \ket { 1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Örnek: Dirac gösterimi ile Hadamard işlemini temsil etme

Aşağıdaki gösterim, genellikle Hadamard kapısını $ \ket { 0 } $ ve 1 ' e $ \ket { } $ ( $ $ $ Bloch Sphere üzerindeki + x ve-x $ yönlerinin birim vektörlerine karşılık gelen) uygulamanın sonuçlarını belirlemek için kullanılır:

$$
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H \ket { 0 } = \ket { + } ,\qquad
\frac{1 } { \sqrt { 2 } } \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} = H 1 \ket { } = \ket { - } .
$$

Bu durumlar Ayrıca, $ \ket { 0 } $ ve $ \ket { 1 } $ toplamı olarak Dirac gösterimi kullanılarak da Genişletilebilir:

$$
\ket{+}= \frac{ 1 } { \sqrt { 2 } } ( \ket { 0 }  +  \ket { 1 } ), \qquad \ket { - } = \frac { 1 } { \sqrt { 2 } } ( \ket { 0 }  -  \ket { 1 } ).
$$

### <a name="computational-basis-vectors"></a>Hesaplama tabanlı vektörler

Bu durum, bu durumların neden genellikle *Hesaplama tabanlı* olarak çağrıldığını gösterir: her hisse maç durumu her zaman hesaplama tabanlı vektörlerin toplamı olarak ifade edilebilir ve bu tür toplamların adı, Dirac gösterimi kullanılarak kolayca ifade edilir  Aynı zamanda bu durum da aynı zamanda geçerlidir $ \ket { + } $ ve hisse Adaları $ \ket { - } $ için de bir temel oluşturur.  Bunu şu şekilde görebilirsiniz:

$$
\ket{0 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ), \qquad \ket { 1 } = \frac { 1 } { \sqrt { 2 } } ( \ket { + }  -  \ket { - } ).
$$

Dirac gösterimi örneği olarak, $ \braket { | } $ $ 0 $ ile 1 arasında iç ürün $ $ olan braket 0 1 ' i düşünün.  Bu, şöyle yazılabilir 

$$
\braket{0 | 1 } = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = 0.
$$

Bu $ \ket { } $ , 0 ve $ \ket { 1 } $ ' in birbirine dik bir vektör olduğunu, yani $ \braket { 0 | 1 } = \braket { 1 | 0 } = 0 $ olduğunu söyler.  Ayrıca, tanım $ \braket { 0 | 0 1 1 1, bu da } = \braket { | } = $ iki hesaplama tabanlı vektörün de *orthonormal* olarak çağrılabilir olması anlamına gelir.

Bu orthonormal özellikleri aşağıdaki örnekte yararlı olacaktır. Durum $ \ket { \psi } = { \frac { 3 } { 5 } } \ket { 1 }  +  { \frac { 4 5 0 ise, } { } } \ket { } $ $ \braket { 1 | 0 0 ' ın 1 } = $ . ölçüm olasılığı $ $ 

$$
\big|\braket{1 | \psi } \big | ^ 2 = \left | \frac { 3 } { 5 } \braket { 1 | 1 }  + \frac { 4 } { 5 } \braket { 1 | 0 } \right | ^ 2 = \frac { 9 } { 25 } .
$$

### <a name="tensor-product-notation"></a>Tensor ürün gösterimi

Dirac gösterimi Ayrıca, içindeki örtük bir Tensor ürün yapısını da içerir.  Bu, hisse alma sırasında iki ilişkili hisse al kaydı tarafından tanımlanan eyalet vektörünün, iki durumlu vektörün tencursor ürünleri olduğundan önemlidir.  Bir hisse veya daha fazla öneme sahip olmak isterseniz, öz, Tensor ürün yapısını açıklayan veya önem taşıyan bir hesaplama açıklanmıştır.  Tensor ürün yapısı, $ \psi \otimes \phi $ her iki hisse alım vektörü için yazabildiğimiz $ \phi $ ve $ \psi $ farklı olarak $ \ket { \psi } \ket { \phi } $ olarak yazılmış, $ \ket { \psi } \otimes \ket { \phi } $ ancak $ \otimes $ vektörler arasında yazma kuralları gereksiz olduğundan, bu, bazen açıkça yazılmış bir durumdur.  Örneğin, sıfır duruma göre başlatılan iki qubits ile durum şu şekilde verilir

$$
\begin{bmatrix}1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { 0 } \otimes \ket { } = \ket { } \ket { } 0 0 0.
$$

Benzer şekilde, $ \ket { } $ tamsayısı için durum p, $ $ ikili gösterimde p tamsayısı kodlayan bir hisse durumu temsil eder $ $ .  Örneğin, $ $ işaretsiz bir ikili kodlama kullanarak 5 sayısını ifade etmek istiyoruz.

$$
\ket{1 } \ket { 0 } \ket { 1 } = \ket { 101 } = \ket { 5 } .
$$

Bu gösterimde $ \ket { 0 ' } $ ın tek qubit durumuna başvurması gerekmez, ancak bunun yerine, 0 ' ın ikili kodlamasını depolayan bir *qubit kayıt* $ $ .  Bu iki gösterimdeki farklar genellikle bağlamdan net değildir.  Bu kural, aşağıdaki yollarla yazılıyolabilen ilk örneği basitleştirmek için yararlıdır:

$$
\begin{bmatrix}1 \\\\ 0 \end{bmatrix} \otimes \cdots \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket { 0 } \otimes \cdots \otimes \ket { 0 0 } = | \cdots 0 0 \rangle = \ket { } ^ { \otimes k 0 } = \ket { } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Örnek: Dirac gösterimi ile süper konumu açıklama

Bir hisse düzeyini anlatmak için Dirac gösterimini nasıl kullanabileceğinizi gösteren başka bir örnek olarak, her bir olası bit dizesi için eşit bir süper konum olan bir hisse $$

$$
H ^ { \otimes n } \ket { 0 } = \frac { 1 } { 2 ^ { n/2 } } \sum _ { j = 0 } ^ { 2 ^ n-1 } \ket { j } = \ket { + } ^ { \otimes n } .
$$

Burada, toplamın 0 ' dan $ $ $ 2 ^ { n } -1 ' i $ $ n $ bit için neden olduğunu merak edebilirsiniz.  İlk olarak, $ { } $ $ n $ bitin gerçekleştirebileceğini 2 ^ n farklı yapılandırma olduğunu unutmayın.  Bu, bir bitin 2 değer sürebilmesini, $ $ ancak iki bitin $ 4 değer alıp bu $ şekilde devam edebilir olduğunu belirterek görebilirsiniz. Genel olarak bu, $ 2 ^ n $ farklı olası bit dizelerinin olduğu, ancak en büyük değerin herhangi birinde $ 1 \cdots 1 = 2 ^ n-1 olduğu $ ve bu nedenle toplamın üst sınırı olduğu anlamına gelir.
Yan bir not olarak, bu $ \ket { + } ^ { \otimes } = \ket { + } $ $ \ket { } ^ { \otimes } = \ket { } $ notational kuralı genellikle her bir qubit, sıfıra başlatıldığından hesaplama bazlı durum için ayrılmış olduğundan, bu örnekte benzerleme vurguladı ile 0 ' a n 0 ' ı kullandık.  Böyle bir kural bu durumda denenirken, hisse bilgi işlem belgelerinde işe alınamaz.

### <a name="expressing-linearity-with-dirac-notation"></a>Dirac gösterimi ile doğrity belirtme

Daha iyi bir Dirac gösterimi özelliği, doğrusal olduğu olgusaldır.  Dört hisse alım durumu vektörü için yazmak istiyorsanız, 

$$( \alpha \ket { \psi }  + \beta \ket { \phi } ) \otimes ( \gamma \ket { \çi }  +  \delta \ket { \omega } ) = \alpha \gamma \ket { \psi } \ket { \ çi }  +  \alpha \delta \ket { \psi } \ket { \omega } + \beta \gamma \ket { \phi } \ket { \ çi } + \beta \delta \ket { \phi } \ket { \omega } .$$

Yani, durum vektörleri arasında tencursor ürünlerinin alınması normal çarpmaya benzer şekilde görünmesi için Dirac gösteriminde Tensor ürün gösterimini dağıtabilirsiniz.

Köşeli vektörler, demet vektörlerine benzer bir kural izler.  Örneğin, vektör $ \bra { \psi } \bra { \phi } $ durum vektörüne $ \psi ^ \dagger \otimes \phi ^ \dagger = ( \psi \otimes \phi ) eşittir \dagger $ . Demet vektörü $ \ket { \psi } $ $ \alpha \ket { 0 1 ise, }  +  \beta \ket { } $ Vector öğesinin köşeli vektör sürümü $ \bra { \psi } = \ket { \psi } ^ \dagger = ( \bra { 0 } \alpha ^ * + \bra { 1 } \beta ^ *) olur $ .

Örnek olarak, durum sayısını $ \ket { \psi } = \frac { } { } \ket { }  +  \frac { } { } \ket { } $ ölçmek için bir hisse programı kullanarak $ \ket { + } $ $ \ket { - } $ 3 5 1 4 5 0 ' ı ölçme olasılığını hesaplamak istediğinizi düşünün. Daha $ sonra, cihazın durumu \ket { - } $ 

$$|\braket{- |\psi}| ^ 2 = \left | \frac { 1 } { \sqrt { 2 } } ( \bra { 0 }  -  \bra { 1 } ) ( \frac { 3 } { 5 } \ket { 1 }  +  \frac { 4 } { 5 } \ket { 0 } ) \right | ^ 2 = \left | - \frac { 3 } { 5 \sqrt { 2 } }  +  \frac { 4 } { 5 \sqrt { 2 } } \right | ^ 2 = \frac { 1 } { 50 } .$$

Negatif işaretin olasılık hesaplamasında görünmesi, hisse alma 'nın klasik bilgi işlem üzerinden daha fazla avantaj elde eden mekanizmalardan biridir.

## <a name="ketbra-or-outer-product"></a>ketya veya dış ürün

Dirac gösterimi ile tartışmak için en son öğe, *ketya* veya dış üründür.  Dış ürün, Dirac gösterimler içinde olarak temsil edilir $ \ket { \psi } \bra { \phi } $ ve bazen, Bras ve kets, brakets olarak ters sırada yapıldığından, bazı durumlarda ketbras olarak adlandırılır.  Dış ürün, $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ hisse durum vektörleri $ \psi $ ve için $ \phi $ matris çarpma aracılığıyla tanımlanır.  Bu gösterimi en basit ve en sık kullanılan örnek,

$$
\ket{0 } \bra { 0 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \begin{bmatrix} 1 & 0 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\\\ 0 & 0 \end{bmatrix} \qquad \ket { 1 } \bra { 1 0 } = \begin{bmatrix} \\\\ 1 \end{bmatrix} \begin{bmatrix} 0 & 1 \end{bmatrix} = \begin{bmatrix} 0 & 0 \\\\ 0 & 1 \end{bmatrix} .
$$

Ketbras, her zaman sabit bir değere bir hisse durumu yansıdığından Projektör olarak adlandırılır.  Bu işlemler Unitary olmadığından (ve bir vektör 'nin norm de korumadığından), bir hisse bilgisayarının bir projektörün bir projektörü kesin bir şekilde uygulayamaması halinde gelmelidir.  Ancak, bir hisse başında ölçüm durumundaki eylemi açıklayan güzel bir iş vardır.  Örneğin, bir durumu 0 olarak ölçyoruz, $ \ket { \psi } $ $ $ ortaya çıkan dönüşüm, ölçüm sonucu olarak durum deneyimlerine

  $$\ket{\psi}\right \frac ok { ( \ket { 0 } \bra { 0 } ) \ket { \psi } } { | \braket { 0 | \psi } | } = \ket { 0 } ,$$

Bunlardan biri, durumu ölçmenizi ve 0 olarak bulmasını bekliyor $ \ket { } $ .  Yeniden yinelemek için, bu tür projektörler bir hisse bir bilgisayardaki bir duruma göre belirlenebilir.  Bunun yerine, $ \ket { } $ bazı sabit olasılığa sahip 0 sonucu ile en iyi şekilde rastgele uygulanabilir.  Bu tür bir ölçünün başarılı olma olasılığı, devlet projektörün beklentisi değeri olarak yazılabilir

$$
\bra{\psi}( \ket { 0 } \bra { 0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2,$$

Bu, projektörlerin ölçüm sürecini ifade etmenin yeni bir yolunu sunışını gösterir.

Bunun yerine, Multi-qubit durumunun ilk qubit durumunu 1 olacak şekilde ölçmemiz durumunda $ , $ Bu işlemi projektör ve Dirac gösterimini kullanarak kolayca de açıklayabilir:

$$
P ( \text { ilk qubit = 1 } ) = \bra { \psi } \left ( \ket { 1 } \bra { 1 veya } \otimes \boldone ^ { \otimes n-1 } \right ) \ket { \psi } .
$$

Burada kimlik matrisi, şu şekilde Dirac gösteriminde kolayca yazılabilir

$$
\boldone= \ket{ 0 } \bra { 0 } + \ket { 1 } \bra { 1 } = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} .
$$

İki-qubit olduğu durumlarda, projektörün şu şekilde genişletilebileceği 

$$
\ket{1 } \bra { 1 1 } \otimes \id = \ket { } \bra { 1 } \otimes ( \ket { 0 } \bra { 0 } + \ket { 1 } \bra { 1 } ) = \ket { 10 } \bra { 10 }  +  \ket { 11 11 } \bra { } .
$$

Daha sonra bunun, sütun vektörü gösterimi kullanılarak multiqubit durumları için ölçüm likelihoods hakkındaki tartışmaya tutarlı olduğunu görebiliriz:

$$
P ( \text { ilk qubit = 1 } ) = \psi ^ \dagger (e \_ { 10 } e \_ { 10 } ^ \dagger + e \_ { 11 } e \_ { 11 } ^ \dagger ) \psi = | e \_ { 10 } ^ \dagger \psi | ^ 2 + | e \_ { 11 } ^ \dagger \psi | ^ 2,$$

Multi-qubit ölçüm tartışmayla eşleşir.  Ancak, bu sonucun Multi-qubit örneğine genelleştirmeye yönelik Genelleştirme, sütun vektörü gösteriminden daha basit olan Dirac gösterimi kullanılarak hızlı bir şekilde daha basittir ve önceki işleme tamamen eşdeğerdir.

## <a name="density-operators"></a>Yoğunluk işleçleri

Dirac gösterimini kullanarak hızlı bir şekilde başka bir yararlı operatör de *durum işleci* olarak da bilinen bir *yoğunluk işleçtir*.
Hisse bir devlet vektörü için bir yoğunluk işleci, $ \rho biçimini alır = \ket { \psi } \bra { \psi } $ .
Durumu bir açıklama yerine matris olarak temsil eden bu kavram, genellikle yararlı olur, çünkü olasılık hesaplamalarını temsil etmek için kullanışlı bir yöntem sunar ve ayrıca bir birinin aynı formalronizde aynı şekilde hem istatistiksel olmayan belirsizlik hem de aynı şekilde, aynı şekilde, aynı şekilde, hem istatistiksel unilkliği hem de
Vektörlerden farklı olarak genel hisse alım işleçleri, bazı hisse bilgi işlem alanlarında ve alanın temel bilgilerini anlamak için gerekli değildir.
İlgilendiğiniz okuyucu için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)' de sunulan başvuru defterlerinden birini okumanızı öneririz.

## <a name="no-locq-gate-sequences-equivalent-to-quantum-states"></a>Q# hisse devletlere eşdeğer kapı dizileri

Hisse gösterimi ve programlama dili hakkında en son bir nokta Q# : Bu belgenin onkümesinde, hisse Eyaleti 'nin hisse bilgi işlem ortamında temel nesne olduğunu belirttik.  Daha sonra Q# , hisse bir değer kavramı olmadığında bir sürpriz olarak gelebilir.  Bunun yerine, tüm durumlar yalnızca bunları hazırlamak için kullanılan işlemler tarafından açıklanmıştır.  Önceki örnek bunun mükemmel bir çizimidir.  Bir kayıttaki her hisse bit dizesinde Tekdüzen üst konumunu ifade etmek yerine, sonucu $ H ^ { \otimes n } \ket { 0 } $ olarak temsil edebilirsiniz.  Bu durumun katlanarak daha kısa olan bu açıklaması yalnızca, bununla ilgili olarak neden olabilecek avantaja sahip olmakla kalmaz, Ayrıca öz, algoritmayı uygulamak için yazılım yığınında yayılması gereken işlemleri tanımlar.  Bu nedenle, Q# hisse durumlarından değil, kapı dizilerini göstermek için tasarlanmıştır; ancak, teorik düzeyinde iki perspektifte eşdeğerdir.
