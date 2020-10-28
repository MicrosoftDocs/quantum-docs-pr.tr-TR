---
Başlık: Pauli ölçümleri açıklaması: tek ve Multi-qubit Pauli ölçüm işlemleriyle nasıl çalışacağınızı öğrenin.
Yazar: bradben uid: Microsoft. hisse. Concepts. Pauli MS. Author: v-benköşeli MS. Date: 12/11/2017 MS. Topic: Makale No-loc:
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

# <a name="pauli-measurements"></a>Pauli ölçümleri

Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.
Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.
İle çalışırken Q# , çalıştırdığınız en yaygın ölçüm türü, diğer tabanlarda ölçümleri dahil etmek üzere hesaplama tabanlı ölçümleri *Pauli measurements* genelleştirmesi ve farklı qugeler arasında eşlik olması olasıdır.
Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $ x, Y, z $ veya $ z \otimes z, x \otimes x, x \otimes Y $ , vb. gibi bir operatör ölçmesi konusunda tartışmak yaygındır.

> [!TIP]
> ' De Q# , Multi-qubit Pauli işleçleri genellikle türündeki diziler tarafından temsil edilir `Pauli[]` .
> Örneğin, $ X Z Y 'yi göstermek için \otimes \otimes $ dizisini kullanabilirsiniz `[PauliX, PauliZ, PauliY]` .

Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır.
İçinde Q# , benzer bir kuralı izliyoruz; artık ölçümlerin bu alternatif görünümünü açıkladık.

Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.
Bir $ n $ -qubit hisse anımız olduğunu düşünün; ardından, bir qubit, $ $ durumun içinde yer aldığı 2 ^ n olasılıkların yarısını ölçmelidir.
Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.
Bu ıntut 'i yansıtmak için ölçüm hakkında düşündüğünüzden bahsede genelleştireceğiz.

Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.
İki alt boşluğu tanımlamanın bir yolu, kural tarafından \pm 1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matrisi belirtmektir $ $ .
Alt boşlukları bu şekilde açıklayan basit bir örnek için Z 'yi düşünün $ $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .
\end{align}
$$

Pauli- $ Z matrisinin köşegen öğelerini okuyarak $ , $ Z 'nin $ $ \ket { } $ $ \ket { } $ karşılık gelen eigenvalues $ \pm 1 ile $ iki eigenvektörün olduğunu, 0 ve 1 olduğunu görebiliriz.
Bu nedenle, qubit ' i ölçyoruz ve `Zero` (0 durumuna karşılık gelir $ \ket { } $ ), qubitin durumunun $ $ Z işlecinin + 1 eigenstate olduğunu biliyoruz $ $ .
Benzer şekilde, elde etmemiz durumunda `One` , qubitimizin durumunun $ Z-1 $ eigenstate olduğunu biliyoruz $ $ . Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $ Z" olarak adlandırılır $ ve hesaplama tabanlı ölçüm gerçekleştirmeyle tamamen eşdeğerdir.

$ \times $ Z 'nin Unitary dönüştürmesi olan 2 2 matrisi $ $ de bu ölçütleri karşılar.
Diğer bir deyişle, $ bir = u ^ \dagger Z u matrisi, a 'nın $ $ $ $ \pm 1 eigenvektörlerinde bir ölçünün iki sonucunu tanımlayan bir matris vermek için başka bir Unitary matrisi $ de kullanabiliriz.
Pauli ölçülerinin gösterimi, $ X, Y, Z $ ölçümlerini bir qubitden bilgi elde etmek için yaptığı eşdeğer ölçümler olarak tanımlayarak bu Unitary denklik 'e başvurur.
Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.


|Pauli ölçüm  | Unitary dönüşümü  |
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $HS ^               {\dagger}$         |

Diğer bir deyişle, bu dil kullanıldığında, "ölçüm $ Y $ ", HS 'yi uygulama $ \dagger $ ve sonra hesaplama temelinde ölçme ile eşdeğerdir; burada [`S`](xref:Microsoft.Quantum.Intrinsic.S) bazen "aşama kapısı" olarak adlandırılan ve Unitary matrisi tarafından benzetilen bir iç hisse dır

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & ı \end{bmatrix} .
\end{align}
$$

Ayrıca, $ HS ^ \dagger $ ' i hisse durumu vektörüne uygulamak ve ardından Z ölçüsüne benzer ve $ $ aşağıdaki işlem ile eşdeğerdir `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Doğru durum daha sonra hesaplama temeline geri dönüştürülmesiyle, bu işlem, her ne kadar ücretli bir vektöre uygulanacak olan miktarları, $ $ Yukarıdaki kod parçacığında otomatik olarak, blok kullanılarak gerçekleştirilir `within … apply` .

' De, sonucu Q# ---, durum---ile etkileşimde bulunmalarından ayıklanan klasik bilgiler j sıfır değeri ile belirtilir ve bu, `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ sonucun $ Pauli işlecinin (-1) ^ j $ eigeninin ölçüldüğü bir değer olup olmadığını gösterir.


## <a name="multiple-qubit-measurements"></a>Birden çok qubit ölçümleri

Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:

$$
Z \otimes z = \begin{bmatrix} 1 & 0 0 0 & & \\\\  0 & -1 & 0 & 0 \\\\ 0 & 0 & -1 & 0 \\\\ 0 0 0 & & & 1 \end{bmatrix} .
$$

Bu nedenle, iki Pauli-Z işleçlerinin Tensor ürünleri, $ $ $ + 1 $ ve $ -1 $ eigenvalues içeren iki boşluktan oluşan bir matris oluşturur.
Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + 1 $ egenine ve kalan yarı $ -1 $ eigenine ait olan bir yarı alan anlamı oluşturur.
Genel olarak, Pauli-Z işleçleri için herhangi bir Tensor ürününün $ ve kimliğin bu ürüne de duyarlı olduğu Tensor ürünü tanımından kolayca bakmak kolaydır $ .
Örneğin,

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 &  0 &  0 &  0 \\\\
        0 &  1 &  0 &  0 \\\\
        0 &  0 & -1 &  0 \\\\
        0 &  0 &  0 & -1 \end{bmatrix} .
\end{align}
$$

Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm 1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar $ .
Örneğin, $ x \otimes x = h \otimes h (z \otimes z) h, \otimes $ $ z = HXH tarafından kullanılan kimlikten h $ .
Tek qubit çalışmasına benzer şekilde, tüm iki-qubit Pauli-ölçümleri $ \dagger \otimes \id $ $ 4 \times 4 $ Unitary $ u için $ u ^ (Z) u olarak yazılabilir. Aşağıdaki tablodaki dönüşümleri numaralandırıyoruz.

> [!NOTE]
>Aşağıdaki tabloda, $ \operatorname { } $ matrisi > göstermek için takas kullanıyoruz$$
> \begin{align}
>     \operatorname{TAKAS et } &=
>     \left( \begin { matris}
>         1 & 0 & 0 & 0 \\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 & 0 & 0 & 1 > \end { matris } \right ) >     \end{align}
> $$
> iç işlemin benzetimini yapmak için kullanılır [`SWAP`](xref:Microsoft.Quantum.Intrinsic) .

|Pauli ölçüm     | Unitary dönüşümü  |
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes Z $ | $ \operatorname { takas } $|
|$\boldone \otimes X $ | $ (H \otimes \boldone ) \operatorname { takas } $|
|$\boldone \otimes Y $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { takas } $|
|$Z \otimes Z $ | $ \operatorname { cnot } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { cnot } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { cnot } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes Y $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes Y $ | $ \operatorname { cnot } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes Y $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

Burada, [`CNOT`](xref:Microsoft.Quantum.Intrinsic.CNOT) işlem aşağıdaki nedenlerden dolayı görüntülenir.
Matrisi içermeyen her Pauli ölçümü, $ \boldone $ $ \otimes Yukarıdaki düşünyana bir Unitary ile z z arasında eşittir $ .
Z z 'nin eigenvalues değeri $ \otimes $ yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'e bağlıdır ve denetlenen işlemler bu eşliği hesaplamak ve ilk bit içinde saklamak için işlem yapar.
İlk bit ölçülene kadar, elde edilen yarı alanın kimliğini kurtararak Pauli işlecinin ölçülesiyle eşdeğerdir.

Tek bir ek notta: ölçü $ z z 'nin, \otimes $ $ z \otimes \mathbb { 1 } $ ve sonrasında $ 1 z \mathbb { } \otimes $ ölçmesi ile aynı olduğunu varsaymaya rağmen bu varsayım yanlış olur.
Bunun nedeni, $ z \otimes z $ 'yi $ $ $ Bu operatörlerin + 1 veya-1 $ egeni olarak ölçmesini ölçmeye yönelik bir durumdur.
$Z \otimes \mathbb { 1 } $ ve daha sonra $ \mathbb { 1 } \otimes z $ , hisse ve $ \otimes \mathbb { } $ sonra $ \mathbb { } \otimes $ 1 z bir yarı boşluk vektörü olan hisse Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.

## <a name="correlations-between-qubits"></a>Kubitler arasındaki bağıntılar
X x veya z z gibi Pauli matrislerini ölçmeye yönelik başka bir $ Yöntem \otimes $ $ \otimes $ de, bu ölçümlerin iki qubit arasındaki bağıntılar içinde depolanan bilgilere bakmasına olanak tanır.
$X ölçme \otimes \id $ , ilk qubit 'de yerel olarak saklanan bilgilere bakmanızı sağlar.
Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin.
Bu, bilgi işlem ortamında, genellikle öğrenmek istediğiniz bilgilerin herhangi bir tek qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve bu nedenle yalnızca bir eklem ölçümü (örn. $ z \otimes z) üzerinden arayarak $ Bu bilgilerin bildirim haline gelmesini gösterir.

Örneğin, hata düzeltilirken, korumamıza çalıştığımız durum hakkında hiçbir şey öğrenirken bir hata oluştuğunu öğrenmek istiyoruz.
[Bit çevirme kod örneği](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) , $ z z \otimes \otimes \id $ ve $ \id \otimes z \otimes z $ < gibi ölçümleri kullanarak bunu nasıl yapakullanabileceğinizi gösteren bir örnek gösterir. --TODO: bunu, bit-çevir kod örneği on-eklenmediyse olduğunda, Samples Browser bağlantısı olarak değiştirin. -->

X Y Z gibi rastgele Pauli işleçleri $ \otimes \otimes \otimes \boldone $ de ölçülebilir.
Pauli işleçlerinin tüm tencursor ürünlerinin her biri yalnızca iki eigenvalues $ \ pm 1 $ ve her ikisi de tüm vektör alanlarının yarı uzayını oluşturur.
Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.

' De Q# , bu tür ölçümler, $ $ ölçü $ (-1) ^ j 'nin egenspace 'e bir sonuç veriyor ise j döndürür $ .
İçinde yerleşik bir özellik olarak Pauli ölçümleri olması Q# yararlı olur, çünkü bu tür işleçler, $ $ işlemi bir Z ve bir Tensor ürünü olarak ifade etmek için gereken diagonalizing U geçidini açıklayan, denetimli olmayan ve temel dönüşümlerde uzun zincirler gerektirir $ $ $ \id $ .
Önceden tanımlanmış Bu ölçülerden birini yapmak istediğinizi belirleyebilmeksizin, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.
Q# sizin için gerekli olan tüm temel dönüştürmeleri otomatik olarak işler.
Daha fazla bilgi için bkz [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) . ve [`MeasurePaulis`](xref:Microsoft.Quantum.Measurement.MeasurePaulis) işlemleri.

## <a name="the-no-cloning-theorem"></a>No-Cloning theorem

Hisse bilgileri güçlüdür.
Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.
Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.
Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya* tarafından verilir.

No-Cloning theorem olarak adlandırılır.
Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.
Bunların kanıtı, genel olarak basittir.
Bu konu başlığı altında, hiçbir ek yardımcı qubit, bizim tartışmamız için çok fazla teknik olmadığı için, kapsamımızda ek bir yardımcı qubitin olmaması durumunda (yardımcı qugeler, bir hesaplama sırasında karalama alanı için kullanılır ve içinde kolayca kullanılır ve yönetilir Q# , bkz. [ödünç alınan qubit](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi tarafından açıklanmalıdır.
Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz.
Kopyalama işleminin benzetimini yapmak için Unitary matrisinin özelliği $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
herhangi bir durum için $ \ket { \psi } $ .
Matris çarpın doğrili özelliği daha sonra tüm ikinci hisse $ \ket { \phi } $

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Bu, No-Cloning ' nin arkasındaki temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az birinde hata almalıdır.
Cloner 'ın giriş durumunda herhangi bir şekilde hareket ederken, bu durum yardımcı qubits 'in eklenmesi ve ölçümü aracılığıyla ihlal edilebilir, ancak bu tür etkileşimler Ayrıca sistem hakkında ölçüm istatistikleri üzerinden bilgi sızıntısına ve bu gibi durumlarda tam kopyalamayı önler.
No-Cloning daha kapsamlı bir kanıtı için, [daha fazla bilgi için](xref:microsoft.quantum.more-information)bkz..

No-Cloning theorem, hisse anından çok büyük bir şekilde kopyalanabileceğinden, hisse durumlarından daha fazla bilgi edinmek için neredeyse yoğun bir özellik veriliyorsa, bu işlem, hisse hesaplamasından oluşan nitel 'yi anlamak için önemlidir.
Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.
Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.
Bu, bir para ve gözbaşları çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla karşılaşmanız durumunda "Ah 'nin dağıtımı $ p = 0.512643 \ Lnoktalarla Bernoulli olmalıdır $ !"  Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.
Benzer şekilde, önceki bilgiler olmadan, bu tür kodların her birini bilmeksizin bir şekilde hazırlayamazmız gibi, bir hisse bilgisini kusursuz bir şekilde klonlayamıyoruz $ $ .

Bilgiler hisse bilgi işlem ortamında ücretsizdir.
Ölçülen her bir qubit, tek bir bilgi verir ve No-Cloning, bu, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan rahatsız edici temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir arka kapı olmadığını gösterir.
