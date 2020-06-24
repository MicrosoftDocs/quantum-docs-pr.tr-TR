---
title: Kuantum bilişiminde vektörler ve matrisler
description: Vektörlerin ve matrislerle nasıl çalışılacağı hakkında temel bilgileri öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269550"
---
# <a name="vectors-and-matrices"></a>Vektörler ve matrisler

Vektör ve matrislerle ilgili bazı benzerlik, hisse bilgi işlem anlamak için önemlidir. Aşağıdaki kısa bir giriş sağlıyoruz ve ilgilendiğiniz okuyucular *, mg, G. (1993) gibi doğrusal algela 'da standart bir başvuruyu okumak için önerilir. Doğrusal algeköşeli giriş (Vol. 3). Kaynak listesi, MA: kaynak Lesley-Cambridge Press* veya [Doğrusal algedeniz](http://joshua.smcvt.edu/linearalgebra/)gibi bir çevrimiçi başvuru.

Boyutun (veya boyutunun) bir sütun vektörü (veya bir [*vektör*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ $n $ , bir $ sütun olarak düzenlenmiş bir $n karmaşık sayılar $ (v_1, v_2, \lnoktalar, V_n) $ koleksiyonudur:

$ $v = \begin{bmatrix}
v_1\\\\
v_2\\\\
\ sanal noktalar\\\\
v_n \end{bmatrix}$$

Vektör $v norm $ $ \sqrt { \ Sum \_ i | v \_ i | ^ 2 } $ olarak tanımlanır. Bir Vector öğesinin normu $1 ise birim norm (ya da bir [*birim vektörü*](https://en.wikipedia.org/wiki/Unit_vector)olarak adlandırılır) olduğu söylenir $ . [*Vector $v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) , $ ^ \dağılım $v gösterilir $ ve $ \* $ karmaşık eşleniği ifade eden aşağıdaki satır vektörü olarak tanımlanmıştır

$ $ \begin{ bmatrix } v_1 \\ \\ \vnoktalar \\ \\ V_n \end{ bmatrix } ^ \hanger = \begin{ bmatrix } v_1 ^ * & \cnoktalar & V_n ^ * \end{bmatrix}$$

İki vektörün birlikte çarpılabilmesinin en yaygın yolu, bir nokta ürünü olarak da bilinen [*iç üründür*](https://en.wikipedia.org/wiki/Inner_product_space).  İç ürün, bir vektörün başka bir vektör için projeksiyonu sağlar ve diğer daha basit vektörler toplamı olarak bir Vector öğesinin nasıl ifade alınacağını açıklamak açısından değerlidir.  $U ve $v arasındaki iç ürün $ $ , belirtilen $ \left \langle u, v \right \rangle $ olarak tanımlanır

$ $ \langle u, v \rangle = u ^ \hanger v = u \_ 1 ^ { \* } v_1 + \cnoktalar + u \_ n ^ { \* } v \_ n.
$$

Bu gösterim Ayrıca bir vektör $v normın $ $ \sqrt { \langle v, v $ olarak yazılmasına izin verir \rangle } .

$Girişleri $c ile çarpıldığı yeni bir vektör oluşturmak için, bir vektörü sayı $c çarpıyoruz $ . Ayrıca, $ $ girdileri $u ve $v girişlerinin toplamı olan yeni bir vektör oluşturmak için $u iki vektör de ekleyebiliriz $v $ $ . Bu işlemler aşağıda gösterilmiştir:

$ $ \mathrm{If } ~ u = \begin{bmatrix}
u_1\\\\
u_2\\\\
\ sanal noktalar\\\\
u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}
    v_1\\\\
    v_2\\\\
    \ sanal noktalar\\\\
    V_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}
au_1 + bv_1\\\\
au_2 + bv_2\\\\
\ sanal noktalar\\\\
au_n + bv_n \end{ bmatrix } .
$$

Bir boyut [*matrisi*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $m \times n $ , $ $ $ aşağıda gösterildiği gibi $m satırlarda ve $n sütunlarında düzenlenmiş $MN karmaşık sayıların bir koleksiyonudur:

$ $M = \begin{bmatrix}
M_ {11 } ~ ~ m_ {12 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cnoktalar ~ ~ m_ {2n } \\ \\ \dnoktalar\\\\
M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cnoktalar ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $

Boyut $n vektörünün $ yalnızca bir boyut matrisi $n \ saat 1 olduğunu unutmayın $ . Vektörlerde olduğu gibi, her girdinin $c çarpıldığı yeni bir matrisi elde etmek için bir matrisi sayı $c çarpabiliriz $ $ ve girişleri iki matrisin ilgili girişlerinin toplamı olan yeni bir matris oluşturmak için aynı boyutta iki matris ekleyebiliriz. 

## <a name="matrix-multiplication-and-tensor-products"></a>Matris çarpma ve Tensor ürünleri

Ayrıca, boyut $ $m \times n $ ve boyutun $N boyut $n \times p ' nin iki matrisi de çarpıp $M $ $ $ $P \times p $ :

\begin{align}
& \begin{bmatrix}
    M_ {11 } ~ ~ m_ {12 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cnoktalar ~ ~ m_ {2n } \\ \\ \dnoktalar\\\\
    M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cnoktalar ~ ~ m_ {MN}
ererbmatrix}
başladıbmatrix}
N_ {11 } ~ ~ N_ {12 } ~ ~ \cnoktalar ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cnoktalar ~ ~ N_ {2p } \\ \\ \dnoktalar\\\\
N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cnoktalar ~ ~ N_ {NP}
\end{ bmatrix } = \begin{bmatrix}
P_ {11 } ~ ~ P_ {12 } ~ ~ \cnoktalar ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cnoktalar ~ ~ P_ {2p } \\ \\ \dnoktalar\\\\
P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cnoktalar ~ ~ P_ {MP}
ererbmatrix}
\end{align}

$P girdileri $ $P _ {ık } = \ sum_j m_ {ij} N_ {JK } $. Örneğin, $P _ {11 $ girdisi, ilk } $N ilk sütunuyla $M ilk satırının iç ürünüdür $ $ . Vector öğesinin yalnızca bir matrisin özel durumu olduğundan, bu tanım matris-vektör çarpörüne genişletilir. 

Göz önünde bulundurmanız gereken tüm matrisler, satır ve sütun sayısının eşit olduğu ve yalnızca $1 sütununa karşılık gelen vektörlerin bulunduğu kare matrisleri olacaktır $ . Tek bir özel kare matrisi, [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix) $ tüm köşegen öğelerinin $1 $ ve kalan öğelerin $0 ' e eşit olması için gösterilen $ \ cıvaalı olarak belirtilen kimlik matrisi ' dir $ :

$ $ \ cıvabitti = \begin{bmatrix}
1 ~ ~ 0 ~ ~ \ cnoktalar ~ ~ 0\\\\
0 ~ ~ 1 ~ ~ \ cnoktalar ~ ~ 0\\\\
~ ~ \dnoktalar\\\\
0 ~ ~ 0 ~ ~ \ cnoktalar ~ ~ 1 \ End{ bmatrix } . $ $

Bir kare matris $A için $ , $ $AB = ba = \ cıvaı 'nin tersi olursa matris $B [*ters*](https://en.wikipedia.org/wiki/Invertible_matrix) bir değer söyliyoruz $ . Bir matrisin tersi de mevcut değildir, ancak mevcut olduğunda, bu, $A ^ {-1 $ olduğunu fark ediyoruz } . 

Tüm matris $M için $ , $M adjoint veya eşleniği devrik $ bir matris $N $ $N _ {ij } = m_ {Ji } ^ \* $. $M adjoint, $ genellikle ^ \ dağılım $M olarak gösterilir $ . $$Uu ^ \linger = [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) u ^ \Linger U = \boldone $ veya equivalently, $U ^ {-1 } = u ^ \ dağılım $ . $U  Belki de Unitary matrislerinin en önemli özelliği, bir vektör 'nin norm düzeyini korumıdır.  Bu durum 

$ $ \langle v, v \rangle = v ^ \hanger v = v ^ \hanger U ^ {-1 } U v = v ^ \hanger u ^ \hanger u v = \langle u v, u v \rangle . $ $  

Matris $M $ , $M = a ^ \linger Ise [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) olarak kabul edilir $ .

Son olarak, iki matrisin $M $m n ve boyutu $N boyut olan [*Tensor ürünü*](https://en.wikipedia.org/wiki/Tensor_product) (veya Kronecker ürünü), $ \times $ $ $p \times q, $P $ \otimes /saat nq boyutunda daha büyük bir dizey $MP $ $ ve $M ile elde edilir $ $ :

\begin{align}
    K \otimes N &= \begin{bmatrix}
        M_ {11 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ \dnoktalar\\\\
        M_ {M1 } ~ ~ \cnoktalar ~ ~ m_ {MN}
    ererbmatrix}
    \otimes \begin{bmatrix}
        N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar\\\\
        N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ}
    \end{ bmatrix } \\ \\ &= \begin{bmatrix}
        M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \ End{ bmatrix } ~ ~ \cnoktalar ~ ~ m_ {1n } \begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{ bmatrix } \\ \\ \dnoktalar\\\\
        M_ {M1 } \ Begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cnoktalar ~ ~ m_ {MN } \ Begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{bmatrix}
    \end{ bmatrix } .
\end{align}

Bu, bazı örneklerde daha iyi gösterilmiştir:

$ $ \begin{bmatrix}
        a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \ End{ bmatrix } = \begin{bmatrix}
        \begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}
        \\\\[1,5 em] b \ Begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}
    ererbmatrix}
    = \begin{ bmatrix } a c \\ \\ a d \\ \\ a \\ \\ b c \\ \\ b d \\ \\ s\end{bmatrix}
$$

ve

$ $ \begin{bmatrix}
        a \ b \\ \\ c \ d \end{bmatrix}
    \otimes \begin{bmatrix}
        e \ f \\ \\ g \ h \end{bmatrix}
     = \begin{bmatrix}
    a\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    kenarı\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    \\\\[1em] c\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    TID\begin{bmatrix}
    e \ f \\\\ g \ h \end{bmatrix}
    ererbmatrix}
    = \begin{bmatrix}
    AE \ AF \ be \ BF \\ \\ AG \ Ah \ bg \ BH \\ \\ CE \ CF \ de \ df \\ \\ CG \ ch \ DG \ DH \ End{ bmatrix } .
$$

Tencursor ürünlerini çevreleyen son yararlı bir notational kuralı, her bir vektör $v $ veya matris $M için $ $v ^ {\otimes n } $ veya $M ^ {\otimes n $ 'ın } $n $ katlamalı bir yinelenen Tensor ürünü için kısa bir seçenektir.  Örneğin:

\begin{align}
& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{1 0 bmatrix } \\ \\ \end{ bmatrix } , \qdörtlü \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qdörtlü \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 1 0 \\ \\ & \ End{ bmatrix } , \qdörtlü \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0 \\ \\ \\ \\ \\\\ \end{bmatrix}&0&1 &0&0&1 &0&0&0 &
\end{align}
