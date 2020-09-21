---
Başlık: hisse Oracles açıklaması: ile nasıl çalışacağınızı ve başka bir algoritmaya girdi olarak kullanılan hisse Oracles, kara Box işlemlerini nasıl tanımlayacağınızı öğrenin.
Yazar: cgranade uid: Microsoft. hisse. Concepts. Oracles MS. Author: chgranad MS. Date: 07/11/2018 MS. Topic: article No-loc:
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
# <a name="quantum-oracles"></a>Hisse Oracles

Oracle $ O $ , başka bir algoritmaya girdi olarak kullanılan "kara kutu" işlemidir.
Genellikle, bu gibi işlemler, $ \\ { \\ } \to \\ { \\ } $ $ n $ bit ikili girişi alan ve bir $ d $ bit ikili çıkış üreten bir klasik işlev olan f: 0, 1 ^ n 0, 1 ^ d kullanılarak tanımlanır.
Bunu yapmak için, belirli bir ikili giriş $ x = (X_ { 0 } , X_ { 1 } , \noktalar, X_ { n-1) } $ göz önünde bulundurun.
Qubit durumlarını $ \ket { \vec { x } } = \ket { X_ { 0 } } \otimes \ket { X_ { 1 } } \otimes \cdots \otimes \ket { X_ { n-1 } } $ olarak etiketleyebilir.

İlk $ $ olarak o $ \ket { x } = \ket { f (x) için o 'yu tanımlamaya çalışır } $ , ancak bu, birkaç soruna neden olabilir.
İlk olarak, $ f 'nin $ farklı bir giriş ve çıkış boyutu ( $ n \ne m) olabilir $ ; Örneğin, $ O da $ kayıttaki qubit sayısını değiştirebilir.
İkincisi, $ n m olsa = bile $ , işlev ters çevrilebilir olmayabilir: $ x y için f (x) = f (y) f (y) $ $ \ne $ , o zaman $ o \ket { x } = o y, o, o & o \ket { } $ $ \dagger \ket { x } \ne o ^ \dagger o \ket { y } $ .
Bu, adeklem işlemi olarak $ ^ ' i oluşturmayacağız \dagger $ ve Oracles için tanımlanmış bir adjoint 'ın olması anlamına gelir.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Bir Oracle 'ı hesaplama tabanlı durumlar üzerinde etkile tanımlama
$Yanıtınızı tutmak için ikinci bir m qubit kaydı sunarak bu sorunlardan her ikisiyle de ilgilenebiliriz $ .
Ardından, Oracle 'ın tüm hesaplama tabanlı durumlarında etkisini tanımlayacağız: tüm $ x \in \\ { 0, 1 \\ } ^ n $ ve $ y \in \\ { 0, 1 \\ } ^ d $ ,

$$
\begin{align}
    O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .
\end{align}
$$

Şimdi de şu anda bu $ = \dagger $ nedenle, daha önceki sorunları çözeceğiz.

> [!TIP]
>$O o {0} = ' yi görmek için { \dagger } $ , $ = \boldone $ $ = $ $ b \in \: :: No-Loc ({)::: 0, 1 \: :: No-Loc (}) $ için \ OPLUS b \ OPLUS b a ile bu o.
>Sonuç olarak, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .

Bu şekilde, her hesaplama tabanlı durum x y için Oracle bu şekilde tanımlamak, $ \ket { } \ket { } $ O zaman $ O gibi $ diğer tüm durumları nasıl davrandığını da tanımlar.
Bu $ $ , tüm hisse işlemleri gibi, üzerinde işlem yaptığı durumunda doğrusal bir şekilde olmak üzere, o kadar her şey için hemen takip eder.
Örneğin, $ h \ket { 0 } = \ket { + } $ ve $ h \ket { 1 } = \ket { - } $ tarafından tanımlanan Hadamard işlemini göz önünde bulundurun.
H 'nin üzerinde nasıl hareket eteceğimizi öğrenmek istiyoruz, $ $ $ \ket { + } $ Bu $ h $ 'nin doğrusal olduğunu kullanabiliriz.

$$
\begin{align}
H \ket { + } & = \frac { 1 } { \sqrt { 2 } } sa ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\
           &= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .
\end{align}
$$

Oracle O sitemizi tanımlama durumunda $ $ benzer şekilde, $ \ket { \psi } $ $ n + m qubits üzerinde herhangi bir durumun şu $ şekilde yazılabileceğini de kullanabilirsiniz

$$
\begin{align}
\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ e } \alpha (x, y) \ket { x } \ket { y}
\end{align}
$$

Burada $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C, } $ durumun katsayılarını temsil eder $ \ket { \psi } $ . Bu nedenle,

$$
\begin{align}
O o \ket { \psi } & = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\
             &= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ e } \alpha (x, y) \ket { x } \ket { y \ OPLUS f (x) } .
\end{align}
$$

## <a name="phase-oracles"></a>Phase Oracles
Alternatif olarak, $ $ $ $ O 'ya giriş temelinde bir _aşama_ uygulayarak bir Oracle 'a f $ 'yi kodlayabiliriz $ . Örneğin, $ o $ gibi $$
\begin{align}
    O \ket { x } = (-1) ^ { f (x) } \ket { x } .
\end{align}
$$
Bir evre, başlangıçta hesaplama tabanlı bir durum x 'te bir yazmaç üzerinde hareket eder $ \ket { } $ , bu aşama genel bir aşamadır ve bu nedenle observable değildir.
Ancak bu tür bir Oracle, bir üst konuma veya denetimli bir işleme uygulandığında çok güçlü bir kaynak olabilir.
Örneğin, $ $ tek bir-qubit işlevi için bir Oracle O_f aşaması düşünün $ $ .
Ni $$
\begin{align}
    O_f \ket{+}
        &=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\
        &=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\
        &=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .
\end{align}
$$

Daha genel olarak, Oracles görünümlerinin her ikisi de yalnızca tek bir bit yerine gerçek sayılar döndüren klasik işlevleri temsil edecek şekilde ayarlanabilir.

Oracle 'ı uygulamak için en iyi yolu seçmek, bu Oracle 'ın belirli bir algoritma içinde nasıl kullanılacağına bağlıdır.
Örneğin, [Deutsch-Jozsa algoritması](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) , Oracle 'ın birinci şekilde uygulandığı, [Grover 'in algoritması](https://en.wikipedia.org/wiki/Grover's_algorithm) ikinci şekilde uygulanan Oracle 'ı temel alır.


Daha fazla ayrıntı için [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465)' deki tartışmayı öneririz.
