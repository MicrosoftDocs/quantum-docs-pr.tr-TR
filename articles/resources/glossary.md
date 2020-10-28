---
Başlık: hisse bilgi işlem sözlüğü açıklaması: hisse kullanımı için kullanılan genel terimler, Eylemler ve nesneler sözlüğü.
Yazar: bradben MS. Author: v-benköşeli MS. Date: 9/1/2020 MS. Topic: article uid: Microsoft. hisse. sözlük No-loc:
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

# <a name="quantum-computing-glossary"></a>Hisse bilgi işlem sözlüğü

## <a name="adjoint"></a>Adjoint

Bir [işlemin](xref:microsoft.quantum.glossary#operation)karmaşık eşleniği devrik. Bir [Unitary](xref:microsoft.quantum.glossary#unitary-operator) işleci uygulayan işlemler için, adjoint işlemin tersidir ve bir dağılım simgesiyle belirtilir. Örneğin, işlem `U` Unitary operatörünü temsil ediyorsa u 'yi $ $ `Adjoint U` temsil eder $ \dagger $ . Daha fazla bilgi için bkz. [adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Anek La

Bir hisse bilgisayarı için geçici bellek görevi gören ve gerektiğinde ayrılan ve ayrılmış bir [qubit](xref:microsoft.quantum.glossary#qubit) .  Daha fazla bilgi için bkz. [birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Zil durumu

İki qubit için en az dört adet en yüksek düzeyde, en önemli [hisse](xref:microsoft.quantum.glossary#quantum-state) [mandan](xref:microsoft.quantum.glossary#entanglement) biri. Dört durum tanımlanmıştır $ \ket { \beta _ { ij } } = ( \mathbb { I } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Bir zil durumu, [EPR çifti](xref:microsoft.quantum.glossary#epr-pair)olarak da bilinir.

## <a name="bloch-sphere"></a>Bloch küre

Üç boyutlu bir birim Sphere öğesinde nokta olarak tek[qubit](xref:microsoft.quantum.glossary#qubit) [hisse durumunun](xref:microsoft.quantum.glossary#quantum-state) grafik gösterimi. Daha fazla bilgi için bkz.  [Bloch Sphere kullanarak qubits ve dönüşümleri görselleştirme](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Çağrılabilir

Dildeki bir [işlem](xref:microsoft.quantum.glossary#operation) veya [işlev](xref:microsoft.quantum.glossary#function) Q# . Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Clienfford grubu

[Şişörün](xref:microsoft.quantum.glossary#bloch-sphere) [Küçlerini ve Pauli işleçleri](xref:microsoft.quantum.glossary#pauli-operators)için efekt permütasyonları kaplayan işlem kümesi. Bunlar [ $ $ X](xref:Microsoft.Quantum.Intrinsic.X), [ $ Y $ ](xref:Microsoft.Quantum.Intrinsic.Y), [ $ Z $ ](xref:Microsoft.Quantum.Intrinsic.Z), [ $ H $ ](xref:Microsoft.Quantum.Intrinsic.H) ve [ $ S $ ](xref:Microsoft.Quantum.Intrinsic.S)işlemlerini içerir.

## <a name="controlled"></a>Tarafından

Hedef işlem için bir veya daha fazla [qubit](xref:microsoft.quantum.glossary#qubit) , etkinleştiriciler [olarak alan bir hisse.](xref:microsoft.quantum.glossary#operation) Daha fazla bilgi için bkz. [denetlenen ve Adjoint işlemleri](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Dirac gösterimi

Aynı zamanda *köşeli ayraç* olarak da adlandırılan [hisse durumlarının](xref:microsoft.quantum.glossary#quantum-state)gösterimini kolaylaştıran bir sembolik kısayol.  *Köşeli* bölüm bir satır vektörünü temsil eder, örneğin bir $ \bra { } = \begin{bmatrix} { _1 a } & { _2 } \end{bmatrix} $ ve *demet* kısmı, $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ bir sütun vektörünü temsil eder. Daha fazla bilgi için bkz. [Dirac gösterimi](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Belirli bir dönüşüme ait bir [egenvector](xref:microsoft.quantum.glossary#eigenvector) sayısının, dönüşüm uygulaması tarafından değiştirildiği faktör.  Bir kare matris $ M $ ve bir eigenvector $ v ve $ sonra, $ = $ $ c $ 'nin eigenvalue olduğu ve herhangi bir bağımsız değişken karmaşık bir sayısı olduğu için MV CV. Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Yönü, belirli bir dönüşüm tarafından değiştirilmeyen ve büyüklüğü, bu vektörün [eigenine](xref:microsoft.quantum.glossary#eigenvalue)karşılık gelen bir faktörle değiştirilmiş olan bir vektör. Kare matris $ M ve bir $ eigenvalue c ve $ $ sonra $ MV = CV $ olmak üzere, burada $ v, $ matrisin bir cgeni vektörü ve herhangi bir bağımsız değişken karmaşık bir sayı olabilir. Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Dolaşıklık

[Qubits](xref:microsoft.quantum.glossary#qubit)gibi hisse parçacıkların birbirleriyle bağımsız olarak açıklanamazlar şekilde *bağlı veya ayrılmış* olabilir. Ölçüm sonuçları, sonsuza kadar ayrıldıklarında bile bağıntılı olur. Entanglement, bir qubit [durumunun](xref:microsoft.quantum.glossary#quantum-state) [ölçülmesi](xref:microsoft.quantum.glossary#measurement) için gereklidir.  Daha fazla bilgi için bkz. [Gelişmiş matris kavramları](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR çifti

İki [qubit](xref:microsoft.quantum.glossary#qubit)için en az dört adet en yüksek düzeyde, en önemli [hisse](xref:microsoft.quantum.glossary#quantum-state) mandan biri. Dört durum tanımlanmıştır $ \ket { \beta _ { ij } } = ( \mathbb { 1 } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Bir EPR çifti, [çan durumu](xref:microsoft.quantum.glossary#bell-state) olarak da bilinir

## <a name="evolution"></a>Ri

[Hisse](xref:microsoft.quantum.glossary#quantum-state) , zaman içinde nasıl değişir. Daha fazla bilgi için bkz. [matris üs öğeleri](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>İşlev
Q#Dilde tamamen klasik (hisse olmayan) bir altyordam türü. İşlevler, hisse algoritmaları içinde kullanıldığında, [qubits](xref:microsoft.quantum.glossary#qubit) veya çağrı [işlemleri](xref:microsoft.quantum.glossary#operation)üzerinde işlem yapılamaz. Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Kapısı

Klasik Logic Gates kavramına bağlı olarak, hisse için bir [işlem](xref:microsoft.quantum.glossary#operation)için eski bir terim. [Hisse](xref:microsoft.quantum.glossary#quantum-circuit-diagram) bağlantı, klasik mantık devrelerinin benzer kavramına bağlı olarak, kapıların (veya işlemlerin) bir ağı olur.

## <a name="global-phase"></a>Küresel aşama

İki [durum](xref:microsoft.quantum.glossary#quantum-state) , bir karmaşık sayının birden çok katı olan $ e ^ i 'ye özdeş { olduğunda \phi } $ , bunlar küresel bir aşamaya göre farklılık gösterir. Yerel aşamaların aksine, genel aşamalar herhangi bir [Measurment](xref:microsoft.quantum.glossary#measurement)üzerinden gözlemlenemez. Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Hadamard işlemi (Hadamard kapısı veya dönüştürme olarak da bilinir), tek bir [qubit](xref:microsoft.quantum.glossary#qubit) üzerinde çalışır ve [superposition](xref:microsoft.quantum.glossary#superposition) $ \ket { } $ $ \ket { } $ qubit başlangıçta $ \ket { 0 } $ durumundaysa, bunu 0 veya 1 ' in hatta bir üst konumuna koyar. Q#' De, bu işlem önceden tanımlı işlem tarafından uygulanır [`H`](xref:Microsoft.Quantum.Intrinsic.H) .

## <a name="immutable"></a>Değişmez

Değeri değiştirilemeyen bir değişken. İçinde değişmez bir değişken Q# , `let` anahtar sözcüğü kullanılarak oluşturulur. Değiştirilebilen değişkenleri bildirmek için *can* , öğesini bildirmek için [kesilebilir](xref:microsoft.quantum.glossary#immutable) anahtar sözcüğünü ve `set` değeri değiştirmek için anahtar sözcüğünü kullanın. 

## <a name="measurement"></a>Ölçüm

Bir gözetmenin sonucunu veren bir [qubit](xref:microsoft.quantum.glossary#qubit) (veya qubits kümesi), klasik bir bit elde eden bir düzenleme. Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Değiştirilebilir

Değeri oluşturulduktan sonra değiştirilmiş olan bir değişken. ' De kesilebilir bir değişken Q# , `mutable` anahtar sözcüğü kullanılarak tanımlanır ve `set` anahtar sözcüğü kullanılarak değiştirilir. Anahtar sözcükle oluşturulan değişkenler `let` [sabittir](xref:microsoft.quantum.glossary#immutable) ve değerleri değiştirilemez.

## <a name="namespace"></a>Ad Alanı

İlgili adların (yani, [işlemler](xref:microsoft.quantum.glossary#operation), [işlevler](xref:microsoft.quantum.glossary#function)ve [Kullanıcı tanımlı türler](xref:microsoft.quantum.glossary#user-defined-type)) toplanması için bir etiket. Örneğin, [Microsoft. hisse. hazırlama](xref:microsoft.quantum.preparation) ad alanı, standart kitaplıkta tanımlanan ve ilk durumları hazırlamaya yardımcı olan tüm sembolleri Etiketler.

## <a name="operation"></a>İşlem

İçindeki temel hisse birimi hesaplaması Q# . Bu, kabaca C, C++ veya Python içindeki bir işleve veya C# ya da Java 'daki statik bir yönteme eşdeğerdir. Daha fazla bilgi için bkz. [işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>İşleç uygulaması

Hisse bir işlem gerçekleştiriliyor. Bu, genellikle geçerli hisse durumu vektörüne bir Unitary matrisi uygular.

## <a name="oracle"></a>Oracle

Çalışma zamanında bir hisse algoritmasına veri bağımlı bilgiler sağlayan bir altyordam. Genellikle amaç, üst konumdaki girişlere karşılık gelen çıkışların [üst konumunu](xref:microsoft.quantum.glossary#superposition) sağlamaktır. Daha fazla bilgi için bkz. [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Kısmi uygulama

Tüm gerekli girişler olmadan bir [işlev](xref:microsoft.quantum.glossary#function) veya [işlem](xref:microsoft.quantum.glossary#operation) çağrılıyor. Bu, gelecekteki bir uygulama sırasında yalnızca eksik parametrelere (alt çizgiyle belirtilir) ihtiyacı olan yeni bir [çağrılabilir](xref:microsoft.quantum.glossary#callable) döndürüyor. Örneğin, işlevi verildiğinde `MyFunc(x : int, y : int) : int {return x + y;}` onu kısmen yeni bir işleve uygulayabilirsiniz `let NewFunc = MyFunc(_, 3)` . Daha sonra yeni işlevi, `NewFunc(2)` *5* değerini döndüren eksik parametre ile daha sonra çağırabilirsiniz.  Daha fazla bilgi için bkz. [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Pauli işleçleri

`X` `Y` Ve hisse işlemleri olarak bilinen 3 2 x 2 Unitary matrisi kümesi `Z` . Kimlik matrisi, $ $ genellikle küme içinde de bulunur.  $I = \begin{bmatrix} 1 & 0 \\\\ 0 & 1 \end{bmatrix} $ , $ X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} $ , $ Y = \begin{bmatrix} 0 & -i \\\\ ı & 0 \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} $ .   Daha fazla bilgi için bkz. [tek qubit işlemleri](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Hisse devre diyagramı

Basit hisse programları için [işlem](xref:microsoft.quantum.glossary#operation) (veya [kapı](xref:microsoft.quantum.glossary#gate)) dizisini grafik olarak temsil eden bir Yöntem (örneğin, 

![Örnek devre diyagramı](~/media/qpe.png). 

Daha fazla bilgi için bkz. [hisse devreleri](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Hisse kitaplıkları

Program oluşturmak için [işlem](xref:microsoft.quantum.glossary#operation), [işlev](xref:microsoft.quantum.glossary#function) ve [Kullanıcı tanımlı türlerin](xref:microsoft.quantum.glossary#user-defined-type) koleksiyonları Q# . [Standart kitaplık](xref:microsoft.quantum.libraries.standard.intro) varsayılan olarak yüklenir. Kullanılabilen diğer kitaplıklar, [Kyatry kitaplığı](xref:microsoft.quantum.chemistry.concepts.intro), [Numerics kitaplığı](xref:microsoft.quantum.numerics.intro) ve [makine öğrenme kitaplığıdır](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Hisse durumu

Yalıtılmış bir hisse sisteminin, [Ölçü](xref:microsoft.quantum.glossary#measurement) olasılıkların ayıklanabileceği kesin durumu. Hisse benzeticisinde, hisse Benzetici, bu bilgileri kullanarak qubits 'in işlemlere nasıl yanıt verdiğini taklit ediyor. Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Klasik bilgi işlem içindeki bir *bite* benzer temel bir hisse bilgisi birimi. Daha fazla bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Yineleme-Until-başarılı

Bilsel olarak başarılı olan bir hisse algoritması. Hata sonrasında, yordam başarılı olana kadar yeniden dener (veya sınıra ulaşılmış olur). Daha fazla bilgi için bkz. [başarılı olana kadar Yinele (ru)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Standart kitaplıklar

Yükleme sırasında derleyici ile birlikte yüklenen [işlemler](xref:microsoft.quantum.glossary#operation), [işlevler](xref:microsoft.quantum.glossary#function) ve [Kullanıcı tanımlı türler](xref:microsoft.quantum.glossary#user-defined-type) Q# . Standart kitaplık uygulamasının hedef makinelere göre belirsiz olması. Daha fazla bilgi için bkz. [Standart kitaplıklar](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Süper konum

Bu, bir [qubit](xref:microsoft.quantum.glossary#qubit) 'in, $ \ket { } $ $ \ket { } $ [ölçülene](xref:microsoft.quantum.glossary#measurement)kadar iki durumun doğrusal bir birleşimi olan (0 ve 1) doğrusal olarak hesaplama kavramıdır.  Daha fazla bilgi için bkz. [hisse kullanımı anlama](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Hedef makine

Soyut bir hisse programını donanım veya benzetim doğrultusunda alçalt bir derleme hedefi. Bu genellikle, geçit değiştirme, hata düzeltme için kodlama, geometrik düzen ve diğerleri gibi birçok amaç için yeniden yazma işlemlerini içerir. Daha fazla bilgi için bkz. [hisse simülatörleri ve ana bilgisayar uygulamaları](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Işınlanma

[Entanglement](xref:microsoft.quantum.glossary#entanglement) ve [ölçüm](xref:microsoft.quantum.glossary#measurement)kullanarak, qubit fiziksel olarak hareket ettirmeden, bir veya daha fazla bir yerde, bir [qubit](xref:microsoft.quantum.glossary#qubit) 'e veri veya [hisse durumu](xref:microsoft.quantum.glossary#quantum-state)oluşturma yöntemi.  Daha fazla bilgi için bkz [. hisse başında hisse ve ilgili](xref:microsoft.quantum.concepts.circuits) küta [.](xref:microsoft.quantum.overview.katas)

## <a name="tuple"></a>Le

Tek bir değer görevi gören virgülle ayrılmış değerler koleksiyonu. Tanımlama grubu *türü* , içerdiği değer türleri tarafından tanımlanır. ' De Q# , tanımlama grupları [sabittir](xref:microsoft.quantum.glossary#immutable) ve iç içe olabilir, diziler içerebilir veya bir dizide kullanılıyor olabilir. Daha fazla bilgi için bkz. [demet türleri](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Unitary işleci

Ters, [adjoint](xref:microsoft.quantum.glossary#adjoint)değerine eşit olan bir işleç, yani $ uu ^ { \dagger } = \id $ .

## <a name="user-defined-type"></a>Kullanıcı tanımlı tür

Tek bir birim olarak başvurulabilen yerleşik veya önceden tanımlanmış türlerin bir koleksiyonu. Daha fazla bilgi için bkz. [Kullanıcı tanımlı türler](xref:microsoft.quantum.guide.types#user-defined-types).