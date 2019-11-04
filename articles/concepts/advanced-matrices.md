---
title: Gelişmiş matris kavramları | Microsoft Docs
description: Gelişmiş matris kavramları
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183769"
---
# <a name="advanced-matrix-concepts"></a>Gelişmiş matris kavramları #

Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues ve Eigenvektör'ler ##

$M $ değerinin kare matris olmasına izin verir ve $v $ tüm sıfır olmayan vektör (yani, tüm girişlerle $0 $ değerine eşit olan vektör) olmayan bir vektör olamaz.

$V [ *$, bazı*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) sayı $c $ $MV = cv $ $M $ If $ olduğunu varsayalım. $C $ eigenvector $v $ öğesine karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım. Genel bir matris $M $ bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir. $V $ eigenvalue $c $ olan bir eigenvector ise, $av $ aynı eigenvalue değerine sahip bir eigenvector (sıfır olmayan $a $) için de aynı zamanda $ olduğunu unutmayın.

Örneğin, kimlik matrisi için her vektör $v, eigenvalue $1 $ içeren bir eigenvector örneğidir.

Diğer bir örnek olarak, köşegen üzerinde yalnızca sıfır olmayan girişler içeren $D bir [*diyagonal matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) düşünün:

$ $ \begin{bmatrix} D_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & D_3 \end{bmatrix}.
$$

Vektörler

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ End {bmatrix} ve \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ End {bmatrix} $ $

Bu matrisin eigenvalues $d _1 $, $d _2 $ ve $d _3 $, sırasıyla. $D _1 $, $d _2 $ ve $d _3 $ farklı sayılardır, bu vektörler (ve bunların katları), matris $D $ olan tek eigenvektörlerdir. Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır. Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörlerini $1 $ değerine eşit bir girişi olan birim vektörleridir ve kalan girişler $0 $ ' e eşittir.

Yukarıdaki örnekte, $D $ öğesinin eigenvektörler $3 $ boyutlu vektörler için temel bir baz olduğunu unutmayın. Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir. Daha açık, $v _1 $, $v _2 $ ve $v _3 $ bir vektör $v $ $v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ $a _1 $, $a _2 $ ve $a _3 $ gibi bir sayı olarak yazılabilir.

Bir hermitian matrisinin (kendi kendine adjoint olarak da adlandırılır), kendi karmaşık eşlenimiyle eşit olan karmaşık bir kare matrisi olduğunu hatırlayın, ancak Unitary matrisi ters bir değer olan karmaşık eşleniği olan karmaşık bir kare matrisi olur.
Yalnızca hisse bilgi işlem sırasında karşılaşılan tek matrisler olan hermitian ve Unitary matrisleri için, aşağıdakileri göz atmak için [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary $M $, Unitary $U $, bazı köşegen matris $D $ için $M = U ^ \linger D U $. Ayrıca, $D $ ' ın köşegen girdileri $M $ öğesinin eigenvalues olur.

Bir diyagonal matris $D $ ' nin eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten biliyoruz. Bu işlemi kullanarak, $v $ 'in eigenvalue $c $, yani $Dv = CV $ olan $D $ öğesinin bir eigenvector olduğunu, daha sonra $U ^ \hanger v $, eigenvalue $M $ olan $c $ öğesinin eigenvector olduğunu biliyoruz. Bunun nedeni

$ $M (U ^ \dağılım v) = U ^ \dağılım D U (U ^ \hanger v) = u ^ \dağılım D (U U ^ \hanger) v = U ^ \hanger D v = c U ^ \hanger v. $ $

## <a name="matrix-exponentials"></a>Matris üs öğeleri
Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.  Bir matrisin $A $ sayısının matris üslü olarak ifade edilebilir

$ $ e ^ A = \ cıvabitti + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \ cnoktalar $ $

Bu önemli bir değer, hermitian matris için $e ^ {IB} $ $B $ için bir Unitary zaman evrimi tarafından açıklandığı için önemlidir.  Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve bu da bu işlemleri tanımlamak için soru-cevap yordamları sunar.
Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.  Bkz [ *. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz.

Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.  Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisi için $A $ bir Unitary $U $ ve $A = U ^ \linger D U $ gibi bir diyagonal matris $D $ olduğunu söyler.  UnitID özellikleri nedeniyle $A ^ 2 = U ^ \dağılım D ^ 2 U $ ve benzer tüm güç $p $ $A ^ p = U ^ \dağılım D ^ p U $ için benzer.  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:

$ $ e ^ A = U ^ \dağılım \left (\ cıvabitti + D + \frac{D ^ 2} {2!} + \cnoktalar \right) U = U ^ \hanger \begin{bmatrix}\exp (D_{11}) & 0 & \cnoktalar & 0\\\\ 0 & \exp (D_{22}) & \cnoktalar & 0\\\\ \vnoktalar & \vnoktalar & \dnoktalar & \vnoktalar\\\\ 0 & 0 & \cnoktalar & \exp (D_ {NN}) \end{bmatrix} U. $ $

Diğer bir deyişle, matrisin eigenine dönüştürmeniz halinde $A $ daha sonra matris üstel değeri, matrisin eigenlerin normal üstel değerini hesaplama ile eşdeğerdir.  Hisse hesaplamalarındaki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu işlem, işlecin üstel düzeyini gerçekleştirmeyi kolaylaştırmak için bir matrisin eigenliğine dönüştürme süreciyle sık görünür ve Trour – bu kılavuzun ilerleyen kısımlarında açıklanan Suzuki stili hisse simülasyonu yöntemleri.

$B $ hem Unitary hem de hermitian, yani, $B = B ^{-1}= B ^ \ dağılım $, $B ^ 2 = \ cıvabitti $ olan başka bir yararlı özelliktir. Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \cıvadone $ ' ı ve $B $ terimlerini birlikte gruplandırarak, herhangi bir gerçek değer için $x $ kimliği olduğunu görebilir.

$ $e ^ {iBx} = \ cıvabitti \ cos (x) + iB\sin (x) $ $


taşıyan. Bu işlem özellikle yararlıdır, çünkü $B $ boyutu, $B $ her ikisi de Unitary ve hermitian olduğunda özel durum için, $ boyutu üstel olsa bile
