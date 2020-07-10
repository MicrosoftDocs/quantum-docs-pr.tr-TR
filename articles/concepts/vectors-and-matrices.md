---
Başlık: hisse bilgi işlem açıklamasında vektörler ve matrisler: vektörlerin ve matrislerle nasıl çalışacağınızı öğrenin.
Yazar: Nicetumwriter uid: Microsoft. hisse. Concepts. vektörms. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. Topic: article No-loc:
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

# <a name="vectors-and-matrices"></a>Vektörler ve matrisler

Vektör ve matrislerle ilgili bazı benzerlik, hisse bilgi işlem anlamak için önemlidir. Aşağıdaki kısa bir giriş sağlıyoruz ve ilgilendiğiniz okuyucular *, mg, G. (1993) gibi doğrusal algela 'da standart bir başvuruyu okumak için önerilir. Doğrusal algeköşeli giriş (Vol. 3). Kaynak listesi, MA: kaynak Lesley-Cambridge Press* veya [Doğrusal algedeniz](http://joshua.smcvt.edu/linearalgebra/)gibi bir çevrimiçi başvuru.

Boyutun (veya boyutunun) bir sütun vektörü (veya basitçe [*vektör*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ , $ bir $ $ $ $ sütun olarak düzenlenmiş n karmaşık sayıların (v_1, v_2, \lnoktalar, V_n) bir koleksiyonudur $ :

$$Yönetim=\begin{bmatrix}
v_1\\\\
v_2\\\\
\ sanal noktalar\\\\
v_n\end{bmatrix}$$

Vektör v 'nin norm $ $ $ \sqrt { \sum \_ i i & m | \_ | } $ ı %2 olarak tanımlanır. Bir Vector öğesinin normu 1 ise birim norm (ya da bir [*birim vektörü*](https://en.wikipedia.org/wiki/Unit_vector)olarak adlandırılır) olduğu söylenir $ $ . [*Vektör v 'nin adeki*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ , $ $ v ^ olarak gösterilir \dagger $ ve $ \* $ karmaşık eşleniği gösterir,

$$\begin{bmatrix}v_1 \\\\ \vnoktalar \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ * & \cdots & V_n ^ *\end{bmatrix}$$

İki vektörün birlikte çarpılabilmesinin en yaygın yolu, bir nokta ürünü olarak da bilinen [*iç üründür*](https://en.wikipedia.org/wiki/Inner_product_space).  İç ürün, bir vektörün başka bir vektör için projeksiyonu sağlar ve diğer daha basit vektörler toplamı olarak bir Vector öğesinin nasıl ifade alınacağını açıklamak açısından değerlidir.  $U ve v arasındaki iç $ ürün $ $ , belirtilen $ \left \langle u, v \right \rangle $ olarak tanımlanır

$$
\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.
$$

Bu gösterim Ayrıca bir vektör v 'nin norm $ $ $ \sqrt { \langle ' i v, v \rangle } $ olarak yazılmasına izin verir.

$ $ Girişleri c ile çarpıldığı yeni bir vektör oluşturmak için, bir vektörü c sayısıyla çarpıyoruz $ $ . Ayrıca, $ $ $ $ girdileri $ u ve v girişlerinin toplamı olan yeni bir vektör oluşturmak için iki $ $ vektör u ve v $ de ekleyebiliriz. Bu işlemler aşağıda gösterilmiştir:

$$\mathrm{} ~ U ise=\begin{bmatrix}
u_1\\\\
u_2\\\\
\ sanal noktalar\\\\
u_n \end{bmatrix} ~ \mathrm { ve}~
Yönetim=\begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \ sanal noktalar\\\\
    V_n \end{bmatrix} , ~ \mathrm { ardından}~
Au + BV=\begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\ sanal noktalar\\\\
au_n + bv_n \end{bmatrix} .
$$

A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) n boyutundaki bir $ matris \times $ , $ $ $ $ $ aşağıda gösterildiği gibi, k satırı ve n $ sütunları halinde düzenlenmiş bir MN karmaşık sayı koleksiyonudur:

$$M= 
\begin{bmatrix}
M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1n}\\\\
M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
\ddots\\\\
M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\
\end{bmatrix}.$$

Boyut n 'nin vektörünün $ $ yalnızca n 1 boyutlu bir matris olduğunu unutmayın $ \times $ . Vektörlerde olduğu gibi, $ $ her girdinin c ile çarpıldığı yeni bir matrisi elde etmek için bir matrisi c sayısıyla çarpabiliriz $ $ ve girişleri iki matrisin ilgili girişlerinin toplamı olan yeni bir matris oluşturmak için aynı boyutta iki matris ekleyebiliriz. 

## <a name="matrix-multiplication-and-tensor-products"></a>Matris çarpma ve Tensor ürünleri

Ayrıca, $ $ $ \times $ $ $ $ \times $ $ $ $ \times Şu şekilde boyut m p $ boyutunda yeni bir matris almak için boyut m n ve n boyut n p 'nin iki matrisi de çarpmak için:

\begin{align}
&\begin{bmatrix}
    M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1n}\\\\
    M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\
    \ddots\\\\
    M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}
\end{bmatrix}
\begin{bmatrix}
N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\
N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\
\ddots\\\\
N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { NP}
\end{bmatrix}=\begin{bmatrix}
P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\
P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\
\ddots\\\\
P_ { M1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { MP}
\end{bmatrix}
\end{align}

$P girişlerinin $ $ P_ { ık } = \sum _j M_ { IJ } N_ { JK } $ . Örneğin, $ P_ 11 ' in { ilk } $ satırı N ilk sütununun iç ürünüdür $ $ $ $ . Vector öğesinin yalnızca bir matrisin özel durumu olduğundan, bu tanım matris-vektör çarpörüne genişletilir. 

Dikkate aldığımız tüm matrisler, satır ve sütun sayısının eşit olduğu ve yalnızca 1 sütuna karşılık gelen vektörlerin bulunduğu kare matrisleri olacaktır $ $ . Tek bir özel kare matrisi, [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix) $ \boldone $ Tüm köşegen öğelerini 1 ' e eşit $ $ ve kalan öğeleri 0 ' a eşit $ $ olan, belirtilen kimlik matrisi ' dir:

$$\boldone=\begin{bmatrix}
1 ~~ 0 ~~ \cdots ~~ 0\\\\
0 ~~ 1 ~~ \cdots ~~ 0\\\\
~~ \ddots\\\\
0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$

Bir kare matris $ a için $ , $ $ AB B 'nin [*ters*](https://en.wikipedia.org/wiki/Invertible_matrix) bir matris olduğunu söyliyoruz $ = = \boldone $ . Bir matrisin tersi de mevcut değildir, ancak mevcut olduğunda, $ bir ^ { -1 olduğunu gösterir } $ . 

Her matris için $ $ , adjoint veya eşleniği devrik, $ $ $ $ $ { IJ } = m_ { Ji N_ } ^ \* $ bir matris N. A 'nın adjoint $ , $ genellikle $ a ^ olarak gösterilir \dagger $ . $ $ [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ Uu ^ \dagger = u ^ \dagger u = \boldone $ veya equivalently, $ u ^ { -1 } = U ^ \dagger $ olan bir matris u olduğunu söyliyoruz.  Belki de Unitary matrislerinin en önemli özelliği, bir vektör 'nin norm düzeyini korumıdır.  Bu durum 

$$\langlev, v \rangle = v ^ \dagger v = v ^ \dagger u ^ { -1 } U v = v ^ \dagger u ^ \dagger u v = \langle u v, U v \rangle .$$  

Bir matris $ d $ , [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) olarak kabul edilir $ = \dagger $ .

Son olarak, m n ve n boyutudaki iki matrisin en büyük matris [*ürünü*](https://en.wikipedia.org/wiki/Tensor_product) (veya Kronecker ürünü), $ $ $ \times $ $ $ $ \times $ MP nq boyutunda daha büyük bir matris $ p = m \otimes $ $ \times $ ve h 'den elde edilir $ $ $ $ :

\begin{align}
    e \otimes N&=
    \begin{bmatrix}
        M_ { 11 } ~~ \cdots ~~ m_ { 1n }\\\\
        \ddots\\\\
        M_ { M1 } ~~ \cdots ~~ m_ { MN  }
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        N_ { 11 } ~~ \cdots ~~ N_ { 1 soru  }\\\\
        \ddots\\\\
        { } ~~ \cdots ~~ PQ N_ N_ P1 {}
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}\\\\
        \ddots\\\\
        M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ } \end{bmatrix} ~~ \cdots  ~~ 
        M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { PQ }  \end{bmatrix}
    \end{bmatrix}.
\end{align}

Bu, bazı örneklerde daha iyi gösterilmiştir:

$$
    \begin{bmatrix}
        a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=
    \begin{bmatrix}
        \begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}
        \\\\[1,5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}
    \end{bmatrix}
    =\begin{bmatrix}c \\\\ a d \\\\ a \\\\ b c \\\\ b d \\\\ s\end{bmatrix}
$$

ve

$$
    \begin{bmatrix}
        a \ b \\\\ c \ d\end{bmatrix}
    \otimes 
    \begin{bmatrix}
        e \ f \\\\ g \ h\end{bmatrix}
     =
    \begin{bmatrix}
    a\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    kenarı\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    TID\begin{bmatrix}
    e \ f \\\\ g \ h\end{bmatrix}
    \end{bmatrix}
    =
    \begin{bmatrix}
    AE \ AF \ olmalıdır \ BF\\\\
    AG \ Ah \ bg \ BH\\\\
    CE \ CF \ de \ df\\\\
    CG \/\ DG \ DH \end{bmatrix} .
$$

Tencursor ürünlerini çevreleyen son yararlı bir notational kuralı, herhangi bir vektör $ v $ veya matris $ d $ , $ v ^ { \otimes n } $ veya $ k ^ n için de { \otimes } $ $ n $ katlama yinelenen bir Tensor ürünü için kısa bir seçenektir.  Örnek:

\begin{align}
&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1- \\\\ 1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\
  &\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 1 & 0 & 0 & 0 \end{bmatrix} .
\end{align}
