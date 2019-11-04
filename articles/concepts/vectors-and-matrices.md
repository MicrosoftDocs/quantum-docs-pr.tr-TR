---
title: Vektörler ve matrisler | Microsoft Docs
description: Vektörler ve matrisler
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 58c96f9cda22b712e1a408e5566e0a8ee987bd6e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183752"
---
# <a name="vectors-and-matrices"></a>Vektörler ve matrisler

Vektör ve matrislerle ilgili bazı benzerlik, hisse bilgi işlem anlamak için önemlidir. Aşağıdaki kısa bir giriş sağlıyoruz ve ilgilendiğiniz okuyucular *, mg, G. (1993) gibi doğrusal algela 'da standart bir başvuruyu okumak için önerilir. Doğrusal algeköşeli giriş (Vol. 3). Kaynak listesi, MA: kaynak Lesley-Cambridge Press* veya [Doğrusal algedeniz](http://joshua.smcvt.edu/linearalgebra/)gibi bir çevrimiçi başvuru.

Boyut (veya boyut) $n $ bir sütun vektörü (veya yalnızca [*vektör*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ karmaşık sayılar $ (v_1, v_2, \lnoktalar, V_n) $ bir sütun olarak düzenlenmiş bir $n koleksiyonudur:

$ $v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vnoktalar\\\\ V_n \end{bmatrix} $ $

$V $ vektörünün norm $ \sqrt{\sum\_ı | v\_i | ^ 2} $ olarak tanımlanır. Bir Vector öğesinin normu $1 $ olması halinde, birim norm (veya bir [*birim vektörü*](https://en.wikipedia.org/wiki/Unit_vector)olarak adlandırılır) olduğu söylenir. $V $ [*vektörünün adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) , ^ \dağılım $ $v gösterilir ve $\*$ karmaşık eşleniği ifade ettiği aşağıdaki satır vektörü olarak tanımlanmıştır

$ $ \begin{bmatrix}v_1 \\\\ \vnoktalar \\\\ V_n \end{bmatrix} ^ \hanger = \begin{bmatrix}v_1 ^ * & \cnoktalar & V_n ^ * \end{bmatrix} $ $

İki vektörün birlikte çarpılabilmesinin en yaygın yolu, bir nokta ürünü olarak da bilinen [*iç üründür*](https://en.wikipedia.org/wiki/Inner_product_space).  İç ürün, bir vektörün başka bir vektör için projeksiyonu sağlar ve diğer daha basit vektörler toplamı olarak bir Vector öğesinin nasıl ifade alınacağını açıklamak açısından değerlidir.  $U $ ve $v $ arasındaki iç ürün, belirtilen $ \ left\langle u, v\solt\rangle $ şöyle tanımlanır

$ $ \langle u, v\rangle = u ^ \kama ger v = u\_1 ^ {\*} v_1 + \cnoktalar + u\_n ^ {\*} v\_n.
$$

Bu gösterim Ayrıca, bir vektör $v $ 'nin norm $ \sqrt{\langle v, v\rangle} $ olarak yazılmasına izin verir.

Girişleri $c $ ile çarpıldığı yeni bir vektör oluşturmak için, bir vektörü $c $ olarak çarpıyoruz. Ayrıca, girdileri $u $ ve $v $ girişlerinin toplamı olan yeni bir vektör oluşturmak için $ ve $v $ $u iki vektör de ekleyebiliriz. Bu işlemler aşağıda gösterilmiştir:

$ $ \mathrm{If} ~ u = \begin{bmatrix} u_1\\\\ u_2\\\\ \vnoktalar\\\\ u_n \end{bmatrix} ~ \mathrm{and} ~ v = \begin{bmatrix} v_1\\\\ v_2\\\\ \vnoktalar @no__ t_10_ \\ V_n \end{bmatrix}, ~ \mathrm{then} ~ au + BV = \begin{bmatrix} au_1 + bv_1\\\\ au_2 + bv_2\\\\ \vnoktalar\\\\ au_n + bv_n \end{bmatrix}.
$$

$M \ saat n $ boyutunda bir [*matris*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) , aşağıda gösterildiği gibi $m $ rows ve $n $ sütunlarında düzenlenmiş $MN $ karmaşık sayıların koleksiyonudur:

$ $M = \begin{bmatrix} m_{11} ~ ~ m_{12} ~ ~ \cnoktalar ~ ~ m_ {1n}\\\\ m_{21} ~ ~ m_{22} ~ ~ \cnoktalar ~ ~ m_ {2n}\\\\ \dnoktalar\\\\ m_ {M1} ~ ~ m_ {m2} ~ ~ \cnoktalar ~ ~ m_ {MN} t_11_ \end{bmatrix}. $ $

$N $ Dimension vektörünün yalnızca bir boyut matrisi $n \times $1 olduğunu unutmayın. Vektörlerde olduğu gibi, her girdinin $c $ ile çarpıldığı yeni bir matrisi elde etmek için bir matrisi sayı $c $ ile çarpabiliriz ve girişleri iki matrisin ilgili girişlerinin toplamı olan yeni bir matris oluşturmak için aynı boyutta iki matris ekleyebiliriz. 

## <a name="matrix-multiplication-and-tensor-products"></a>Matris çarpma ve Tensor ürünleri

Ayrıca, aşağıdaki gibi $M $ boyut $m \times n $ ve $N $ boyut $n \times p $ $P, aşağıdaki gibi

\begin{hizalaması} & \begin{bmatrix} m_{11} ~ ~ m_{12} ~ ~ \cnoktalar ~ ~ m_ {1n}\\\\ m_{21} ~ ~ m_{22} ~ ~ \cnoktalar ~ ~ m_ {2n}\\\\ \dnoktalar\\\\ m_ {M1} ~ ~ m_ {m2} ~ ~ \cnoktalar ~ ~ m_ {MN} \end{bmatrix} \ {bmatrix} N_{11} ~ ~ N_{12} ~ ~ \cnoktalar ~ ~ N_ {1p}\\\\ N_{21} ~ ~ N_{22} ~ ~ \cnoktalar ~ ~ N_ {2p}\\\\ \dnoktalar\\\\ N_ {N1} ~ ~ N_ {N2} ~ ~ \cnoktalar ~ ~ N_ {NP} \end{bmatrix} = \begin{bmatrix} P_{11} ~ ~ P_{12} ~ ~ \cnoktalar ~ ~ P_ {1p}\\\\ P_{21} ~ ~ P_{22} ~ ~ \cnoktalar ~ ~ P_ {2p}\\\\ \dnoktalar\\\\ P_ {M1} ~ ~ P_ {m2} ~ ~ \cnoktalar ~ ~ P_ {MP} \end{bmatrix} \end{hizalaması}

$P $ girişlerinin $P _ {ık} = \sum_j m_ {ij} N_ {JK} $ olduğu yerdir. Örneğin, $P _{11}$ girişi, ilk $N $ sütunundaki $M $ satırının iç ürünüdür. Vector öğesinin yalnızca bir matrisin özel durumu olduğundan, bu tanım matris-vektör çarpörüne genişletilir. 

Dikkate aldığımız tüm matrisler, satır ve sütun sayısının eşit olduğu ve yalnızca $1 $ sütununa karşılık gelen vektörlerin bulunduğu kare matrisleri olacaktır. Tek bir özel kare matrisi, tüm köşegen öğelerinin $1 $ değerine eşit ve kalan öğelerin $0 $ değerine eşit olduğu, belirtilen $ \cıvadone $ [*kimlik matrisine*](https://en.wikipedia.org/wiki/Identity_matrix)sahiptir:

$ $ \ cıvadone = \begin{bmatrix} 1 ~ ~ 0 ~ ~ \cnoktalar ~ ~ 0\\\\ 0 ~ ~ 1 ~ ~ \cnoktalar ~ ~ 0\\\\ ~ ~ \dnoktalar\\\\ 0 ~ ~ 0 ~ ~ \cnoktalar ~ ~ 1 \ End{bmatrix}. $ $

$A $ kare matrisi için, bir matris $B $ $AB = BA = \cıvadone $ ise [*ters*](https://en.wikipedia.org/wiki/Invertible_matrix) bir değer söyliyoruz. Bir matrisin tersi de mevcut değildir, ancak mevcut olduğunda, bu, $A ^{-1}$ olduğunu fark ediyoruz. 

Her matris $M $ için, $M $ 'ın adekor eşleniği devrik bir matris $N $, $N _ {ij} = m_ {Ji} ^\*$. $M $ öğesinin adjoint, genellikle ^ \hanger $ $M olarak gösterilir. $UU ^ \linger = U [](https://en.wikipedia.org/wiki/Unitary_matrix) ^ \Linger U = \cıvas $ veya equivalently, $U ^{-1} = U ^ \linger $. $U  Belki de Unitary matrislerinin en önemli özelliği, bir vektör 'nin norm düzeyini korumıdır.  Bu durum 

$ $ \langle v, v \rangle = v ^ \gesger v = v ^ \hanger U ^{-1} U v = v ^ \gesger U ^ \hanger U v = \langle U v, U v\rangle. $ $  

Bir matris $M $, $M = d ^ \linger $ ise [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) olarak kabul edilir.

Son olarak, iki matrisin (ya da Kronecker ürünü) $M $ boyutu $m \times n $ $N ve boyut $p \times q [ *$, $P*](https://en.wikipedia.org/wiki/Tensor_product) $ ve $MP $ ' den aşağıdaki gibi elde edilir:

\begin{hizalaması} g \otimes N & = \begin{bmatrix} m_{11} ~ ~ \cnoktalar ~ ~ m_ {1n} \\\\ \dnoktalar\\\\ m_ {M1} ~ ~ \cnoktalar ~ ~ m_ {MN} \end{bmatrix} \otimes \begin{bmatrix} N_{11} ~ ~ \cnoktalar ~ ~ N_ {1Q}\\\\ \dnoktalar @no__ t_8_ \\ N_ {P1} ~ ~ \cnoktalar ~ ~ N_ {PQ} \end{bmatrix}\\\\ & = \begin{bmatrix} m_{11} \begin{bmatrix} N_{11} ~ \ cnoktalar ~ ~ N_ {1Q}\\\\ \dnoktalar\\\\ N_ {P1} ~ ~ \cnoktalar ~ ~ N_ {PQ} \end{bmatrix} ~ ~ \cnoktalar ~ ~ m_ {1n} \begin{bmatrix} N_{11} ~ ~ \cnoktalar ~ ~ N_ {1Q}\\\\ \dnoktalar\\\\ N_ {P1} ~ ~ \cnoktalar ~ ~ N_ {PQ} \end{bmatrix}\\\\ \dnoktalar\\\\ m_ {M1} \begin{bmatrix} N_{11} ~ ~ \ cnoktalar ~ ~ N_ {1Q}\\\\ \dnoktalar\\\\ N_ {P1} ~ ~ \cnoktalar ~ ~ N_ {PQ} \end{bmatrix} ~ ~ \cnoktalar ~ ~ m_ {MN} \begin{bmatrix} N_{11} ~ ~ \cnoktalar ~ ~ N_ {1Q}\\\\ \dnoktalar\\\\ N_ {P1} ~ ~ \cnoktalar ~ ~ N_ {PQ} \end {bmatrix} \end{bmatrix}.
\end{hizalaması}

Bu, bazı örneklerde daha iyi gösterilmiştir:

$ $ \begin{bmatrix} a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix} a \begin{bmatrix} c \\\\ d \\\\ e \ End{bmatrix} @no__ t_10_ \\[1,5 em] b \ Begin{bmatrix} c \\\\ d \\\\ e\end {bmatrix} \end{bmatrix} = \begin{bmatrix} a \\\\ a \\\\ b c \\\\ b d \\\\ be\end {bmatris} $ $

'nı ve

$ $ \begin{bmatrix} a \ b \\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\g \ h \end{bmatrix} = \begin{bmatrix} a\begın {bmatrix} e \ f\\\\ g \ h \ End{bmatrix} b\begın {bmatrix} e \ f\\@no__ t_7_ g \ h \end{bmatrix} \\\\[1em] c\begın {bmatrix} e \ f\\\\ g \ h \end{bmatrix} d\begın {bmatrix} e \ f\\\\ g \ h \end{bmatrix} \end{bmatrix} = \begin{bmatrix} AE \ AF \ in \ BF \\@no__ t_15_ AG \ Ah \ bg \ BH \\\\ CE \ CF \ de \ df \\\\ CG \ ch \ DG \ DH \ End{bmatrix}.
$$

Tensor ürünlerini çevreleyen son yararlı bir notational kuralı, her bir vektör $v $ veya matris $M $, $v ^ {\otimes n} $ veya $M ^ {\otimes n} $, $n $-katlama yinelenen bir Tensor ürünü için kısa bir seçenektir.  Örnek:

\begin{hizalaması} & \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \ End{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\-1 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 1 \\\\-1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ & \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ {\otimes 1} = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}, \qquad\begin{bmatrix} 0 & 1 \\@no__ t_27_ 1 & 0 \end{bmatrix} ^ {\otimes 2} = \begin{bmatrix} 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0\\\\ 1 & 0 & 0 & 0 \ End {bmatrix}.
\end{hizalaması}

