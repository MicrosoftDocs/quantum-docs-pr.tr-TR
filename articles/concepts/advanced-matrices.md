---
title: Gelişmiş matris kavramları
description: Hisse algoritmaları anlatmak ve benzetimini yapmak için kullanılan temel araçlar olan eigenvektörler, eigenvalues ve matris üsleri hakkında bilgi edinin.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
- $$
- $$
- $$
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
ms.openlocfilehash: 71923247121eae6a1d4e26d2664d8e547370ba3a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269465"
---
# <a name="advanced-matrix-concepts"></a>Gelişmiş matris kavramları #

Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues ve Eigenvektör'ler ##

$M $ kare matris olmasına izin verir ve $ Tüm sıfırlardan oluşan vektör (yani, tüm girdileri $0 ' e eşit olan vektör) olmayan bir vektör olarak $v $ .

$V $ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) bir $ sayı $c için $Mv = MF olursa $M eigenvector ' in olduğunu varsayalım $ $ . $C $ eigenvector $v karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ . Genel bir matris $M $ bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir. $V $ , eigenvalue $c sahip bir eigenvector ise $ , $av $ $ aynı eigenvalue değerine sahip bir eigenvector (sıfır olmayan $a için) de olduğunu unutmayın.

Örneğin, kimlik matrisi için her vektör $v, $ eigenvalue $1 ile bir eigenvector değildir $ .

Diğer bir örnek olarak, diyagonal bir [*matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D göz önünde bulundurun $ ve yalnızca köşegen üzerinde sıfır olmayan girişler bulunur:

$ $ \begin{bmatrix}
d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .
$$

Vektörler

$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} ve \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$

Bu matrisin eigenvalues $d _1 $ , $d _2 $ ve $d _3 $ sırasıyla). $D _1 $ , $d _2 $ ve $d _3 $ farklı sayılardır, bu vektörler (ve bunların katları), matris $D için yalnızca egenvektörlerdir $ . Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır. Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörler, $1 'e eşit bir girişi olan birim vektörleridir $ ve kalan girişler $0 ' e eşittir $ .

Yukarıdaki örnekte, $D 'in eigenvektörler $ $3 boyutlu vektörler için bir temel oluşturacak $ . Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir. Daha açık, $v _1 $ , $v _2 $ ve $v _3, $ herhangi bir vektör $v $v $ = a_1 v_1 + a_2 v_2 + a_3 v_3, $a $a, $a $ $ _2 $ ve _3 olarak yazılabilir $ .

Bir hermitian matrisinin (kendi kendine adjoint olarak da adlandırılır), kendi karmaşık eşlenimiyle eşit olan karmaşık bir kare matrisi olduğunu hatırlayın, ancak Unitary matrisi ters bir değer olan karmaşık eşleniği olan karmaşık bir kare matrisi olur.
Yalnızca hisse hesaplamasından kaynaklanan tek matrisler olan hermitian ve Unitary matrisleri için, şunları göz atmak gereken [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary $M için $ , bir $ $ çapraz matris $D $M = U ^ \linger D U gibi bir Unitary $U var $ . Ayrıca, $D çapraz girdileri $ $M eigenvalues olacaktır $ .

Bir diyagonal matris $D eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten biliyoruz $ . Bu işlemi kullanarak, $v $ $ eigenvalue $c, yani $DV = CV içeren bir $D eigenvector vektörü olduğunu $ $ , $U ^ \dağılım v ' $ nin $ eigenvalue $M sahip bir $c eigenvector olacağını biliyoruz $ . Bunun nedeni

$ $M (U ^ \dağılım v) = U ^ \dağılım D U (U ^ \hanger v) = u ^ \dağılım D (U U ^ \hanger) v = U ^ \hanger D v = c U ^ \hanger v. $ $

## <a name="matrix-exponentials"></a>Matris üs öğeleri
Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.  Matris $A matris üstel $ olarak ifade edilebilir

$ $ e ^ A = \ cıvabitti + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \ cnoktalar $ $

Bu önemli bir değer, hermitian matrisi için $e ^ {IB } $ $B matris için bir Unitary zaman evrimi tarafından açıklandığı için önemlidir $ .  Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve bu da bu işlemleri tanımlamak için soru-cevap yordamları sunar.
Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.  Bkz [*. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz..

Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.  Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisi için $A $ bir Unitary matris $U $ ve köşegen matris $D $ $A = U ^ \dağılım D U gibi bir şekilde olduğunu söylüyor $ .  UnitID özellikleri nedeniyle $A ^ 2 = U ^ \dağılım D ^ 2 U $ ve herhangi bir güç $p için benzer $ $A ^ p = u ^ \Dağılım d ^ p u $ .  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:

$ $ e ^ A = U ^ \dağılım \left (\cıvadone + D + \frac{D ^ 2 } {2!} + \ cnoktalar \ sağ) U = u ^ \dağılım \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cnoktalar &0 \\\\ 0 & \exp (D_ {22 } ) & \cnoktalar & 0 \\\\ \vnoktalar & \vnoktalar & \dnoktalar & \vnoktalar \\\\ 0&0 & \ cnoktalar & \exp (D_ {nn } ) \end{ bmatrix } U. $ $

Diğer bir deyişle, matrisin eigenine dönüştürmeniz durumunda $A matris $ üstel değeri, matrisin eigenlik değerlerinin normal üstel değerini hesaplama ile eşdeğerdir.  Hisse bilgi işlem içindeki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu arada, işleç üstel özelliğinin gerçekleştirilmesini kolaylaştırmak için bir matrisin eigenliğine dönüştürülmesi, bu kılavuzda sık görülen ve bu kılavuzun ilerleyen bölümlerinde ele alınan Trour – Suzuki-Style hisse

Diğer bir yararlı özellik $B $ hem Unitary hem de hermitian, yani $B = b ^ {-1 } = b ^ \ dağılım $ $B ^ 2 = \ cıvabitti $ . Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \ cıvalanma $ ve $B $ terimlerini birlikte gruplandırarak, kimlik $x herhangi bir gerçek değer için bu değeri görebilirsiniz $ .

$ $e ^ {iBx } = \cıvadone \cos (x) + iB\sin (x) $ $


taşıyan. Bu işlem özellikle yararlıdır çünkü $B boyutu üstel olarak büyük olsa bile, $ $B $ hem Unitary hem de hermitian olduğu zaman özel durum için
