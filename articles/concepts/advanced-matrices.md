---
Başlık: Gelişmiş matris kavramları açıklaması: hisse algoritmalarından bahseve benzetimini yapmak için kullanılan temel araçlar olan eigenvektörler, eigenvalues ve matris üsleri hakkında bilgi edinin.
Yazar: Histumwriter uid: Microsoft. hisse. Concepts. Matrix-Gelişmiş MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. Topic: article No-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Gelişmiş matris kavramları #

Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues ve Eigenvektör'ler ##

$ $ Bir kare matris ve $ v $ 'nin tüm sıfır olmayan vektör (yani, tüm girdileri 0 ' a eşit olan vektör) olmayan bir vektör $ $ olmasına izin verin.

C 'nin $ $ bir sayı ise, f CV ise M 'nin [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ $ $ = $ $ $ . $C $ 'nin eigenvector v öğesine karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ $ . Genel olarak bir matris $ $ , bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir. $V $ , eigenvalue c ile bir eigenvector ise $ $ , $ av $ 'nin $ $ aynı eigenvalue ile aynı zamanda bir eigenvector (sıfır olmayan a için) olduğunu unutmayın.

Örneğin, kimlik matrisi için her vektör $ v, $ eigenvalue 1 içeren bir eigenvector değeridir $ $ .

Diğer bir örnek olarak, [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ $ köşegen üzerinde yalnızca sıfır olmayan girdilerin bulunduğu diyagonal bir matrisi göz önünde bulundurun:

$$
\begin{bmatrix}
d_1 0 0 0 & & \\\\ & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix} .
$$

Vektörler

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} ve \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

Bu matrisin eigenvalues $ D_1 $ , $ d_2 $ ve $ D_3 $ sırasıyla. $D_1 $ , $ d_2 $ ve $ D_3 $ birbirinden farklı sayısa, bu vektörler (ve bunların katları) d matrisinin yalnızca emoji vektörleridir $ $ . Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır. Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörlerini 1 ' e eşit olan birim vektörleridir $ $ ve kalan girişler 0 ' a eşittir $ $ .

Yukarıdaki örnekte, D 'nin egenvektörler 'in $ $ $ 3 $ boyutlu vektörler için temel olduğunu unutmayın. Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir. Daha açık, $ v_1 $ , $ v_2 $ ve $ v_3 $ bir vektör $ v $ $ = $ 'nin, v_1 $ $ , $ a_2 $ ve $ v_2 $ bazı sayılar için v A_1 a_3 + v_3 A_1 + a_2 a_3 olarak yazılabilmesini sağlayabilirsiniz.

Bir hermitian matrisinin (kendi kendine adjoint olarak da bilinir), kendi karmaşık eşleniği için eşit olan karmaşık bir kare matrisi olduğunu anımsayın, ancak Unitary matrisi ters, adjoint veya karmaşık eşleniği devrik değerine eşit olan karmaşık bir kare matrisi olur.
Yalnızca hisse hesaplamasından kaynaklanan tek matrisler olan hermitian ve Unitary matrisleri için, şunları göz atmak gereken [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary 3 $ $ $ $ $ = \dagger $ $ $ . Ayrıca, D 'nin çapraz girdileri $ $ M 'nin eigenvalues değeri olacaktır $ $ .

Bir diyagonal matris D 'nin eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten $ biliyoruz $ . Bu işlemi kullanarak, $ v 'nin $ $ $ eigenvalue c, yani DV CV ile D 'nin bir egenvector olduğunu, $ $ yani $ = $ $ U ^ \dagger v 'nin $ $ $ eigenvalue c ile M 'nin eigenvector $ $ olduğunu biliyoruz. Bunun nedeni

$$M (U ^ \dagger v) = u ^ \dagger d U (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ d \dagger v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Matris üs öğeleri
Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.  Bir matrisin a 'nın matris üsleri, $ $ şöyle ifade edilebilir

$$
e ^ a = \boldone + a + \frac { ^ 2 } { 2! } + \frac { Bir ^ 3 } { 3!}+\cdots
$$

Bu önemli bir öneme sahip olduğundan, hisse ve saat evriminin $ { } $ B hermitian matrisi için e ^ IB biçiminde $ bir Unitary matrisi tarafından açıklandığından bu önemlidir $ .  Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve Q# Bu da bu işlemleri tanımlamaya yönelik iç yordamlar sunar.
Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.  Bkz [*. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz..

Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.  Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisinin $ bir $ unitöğeli matris $ U $ ve $ $ $ = u ^ \dagger D u gibi $ diyagonal bir matris olduğunu söylüyor.  UnitID özellikleri nedeniyle, bir $ ^ 2 = u ^ \dagger d ^ 2 u $ ve benzer şekilde herhangi bir Power $ p $ $ a ^ p = u ^ \dagger d ^ p u olabilir $ .  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) & \cdots & 0 \\\\ \vnoktalara & \vnoktalara & \ddots & \vnoktalar \\\\ 0 & 0 & \cdots & \ exp (D_ { nn } ) \end{bmatrix} U.$$

Diğer bir deyişle, matrisin eigenine dönüştürmeniz halinde matris $ $ üstel değeri, matrisin eigendeğerlerinin normal üstel değerini hesaplama ile eşdeğerdir.  Hisse bilgi işlem içindeki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu arada, işleç üstel özelliğinin gerçekleştirilmesini kolaylaştırmak için bir matrisin eigenliğine dönüştürülmesi, bu kılavuzda sık görülen ve bu kılavuzun ilerleyen bölümlerinde ele alınan Trour – Suzuki-Style hisse

$B $ 'nin hem Unitary hem de hermitian, yani b $ = b ^ { -1 } = B ^, \dagger $ $ b ^ 2 = \boldone $ olması başka bir yararlı özelliktir. Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \boldone $ ve $ B $ terimlerini birlikte gruplandırarak, tüm gerçek değer $ x için kimlik olduğunu görebilir $

$$e ^ { ibx } = \boldone \cos (x) + ib\sin (x)$$


taşıyan. Bu işlem özellikle yararlıdır çünkü b boyutu, b 'nin $ $ $ $ hem Unitary hem de hermitian olduğu durumlarda özel durum için, b boyutu üstel olarak büyük olsa bile,
