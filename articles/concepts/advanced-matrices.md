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
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="8b9f3-103">Gelişmiş matris kavramları</span><span class="sxs-lookup"><span data-stu-id="8b9f3-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="8b9f3-104">Artık, bir dizi algoritmalarınızı anlatmak ve uygulamak için ihtiyaç duyduğumuz temel bir araç kümesini oluşturan [*Eigenvalues, Eigenvektörler*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) ve [*üs ve üslerin*](https://en.wikipedia.org/wiki/Matrix_exponential) sağlığımızı genişlettik.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="8b9f3-105">Eigenvalues ve Eigenvektör'ler</span><span class="sxs-lookup"><span data-stu-id="8b9f3-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="8b9f3-106">$M $ kare matris olmasına izin verir ve $ Tüm sıfırlardan oluşan vektör (yani, tüm girdileri $0 ' e eşit olan vektör) olmayan bir vektör olarak $v $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="8b9f3-107">$V $ [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) bir $ sayı $c için $Mv = MF olursa $M eigenvector ' in olduğunu varsayalım $ $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="8b9f3-108">$C $ eigenvector $v karşılık gelen [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) olduğunu varsayalım $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="8b9f3-109">Genel bir matris $M $ bir vektörü başka bir vektöre dönüştürebilir, ancak bir sayı ile Çarpılmakta olduğu sürece değişmeden bırakıldığı için bir eigenvector özeldir.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="8b9f3-110">$V $ , eigenvalue $c sahip bir eigenvector ise $ , $av $ $ aynı eigenvalue değerine sahip bir eigenvector (sıfır olmayan $a için) de olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="8b9f3-111">Örneğin, kimlik matrisi için her vektör $v, $ eigenvalue $1 ile bir eigenvector değildir $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="8b9f3-112">Diğer bir örnek olarak, diyagonal bir [*matris*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D göz önünde bulundurun $ ve yalnızca köşegen üzerinde sıfır olmayan girişler bulunur:</span><span class="sxs-lookup"><span data-stu-id="8b9f3-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="8b9f3-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8b9f3-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="8b9f3-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="8b9f3-115">Vektörler</span><span class="sxs-lookup"><span data-stu-id="8b9f3-115">The vectors</span></span>

<span data-ttu-id="8b9f3-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end{bmatrix} ve \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="8b9f3-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="8b9f3-117">Bu matrisin eigenvalues $d _1 $ , $d _2 $ ve $d _3 $ sırasıyla).</span><span class="sxs-lookup"><span data-stu-id="8b9f3-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="8b9f3-118">$D _1 $ , $d _2 $ ve $d _3 $ farklı sayılardır, bu vektörler (ve bunların katları), matris $D için yalnızca egenvektörlerdir $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="8b9f3-119">Genel olarak, çapraz matris için, eigenvalues ve eigenvektörleri okumak kolaydır.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="8b9f3-120">Eigenvalues, köşegen üzerinde görünen tüm numaralardır ve ilgili eigenvektörler, $1 'e eşit bir girişi olan birim vektörleridir $ ve kalan girişler $0 ' e eşittir $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="8b9f3-121">Yukarıdaki örnekte, $D 'in eigenvektörler $ $3 boyutlu vektörler için bir temel oluşturacak $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="8b9f3-122">Bu, herhangi bir Vector öğesinin doğrusal bir birleşimi olarak yazılabilmesini sağlayan bir vektör kümesidir.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="8b9f3-123">Daha açık, $v _1 $ , $v _2 $ ve $v _3, $ herhangi bir vektör $v $v $ = a_1 v_1 + a_2 v_2 + a_3 v_3, $a $a, $a $ $ _2 $ ve _3 olarak yazılabilir $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="8b9f3-124">Bir hermitian matrisinin (kendi kendine adjoint olarak da adlandırılır), kendi karmaşık eşlenimiyle eşit olan karmaşık bir kare matrisi olduğunu hatırlayın, ancak Unitary matrisi ters bir değer olan karmaşık eşleniği olan karmaşık bir kare matrisi olur.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="8b9f3-125">Yalnızca hisse hesaplamasından kaynaklanan tek matrisler olan hermitian ve Unitary matrisleri için, şunları göz atmak gereken [*Spectral teoreminin*](https://en.wikipedia.org/wiki/Spectral_theorem)olarak bilinen genel bir sonuç vardır: herhangi bir hermitian veya Unitary $M için $ , bir $ $ çapraz matris $D $M = U ^ \linger D U gibi bir Unitary $U var $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="8b9f3-126">Ayrıca, $D çapraz girdileri $ $M eigenvalues olacaktır $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="8b9f3-127">Bir diyagonal matris $D eigenvalues ve eigenvektörlerini nasıl hesapladığımimizi zaten biliyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="8b9f3-128">Bu işlemi kullanarak, $v $ $ eigenvalue $c, yani $DV = CV içeren bir $D eigenvector vektörü olduğunu $ $ , $U ^ \dağılım v ' $ nin $ eigenvalue $M sahip bir $c eigenvector olacağını biliyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="8b9f3-129">Bunun nedeni</span><span class="sxs-lookup"><span data-stu-id="8b9f3-129">This is because</span></span>

<span data-ttu-id="8b9f3-130">$ $M (U ^ \dağılım v) = U ^ \dağılım D U (U ^ \hanger v) = u ^ \dağılım D (U U ^ \hanger) v = U ^ \hanger D v = c U ^ \hanger v. $ $</span><span class="sxs-lookup"><span data-stu-id="8b9f3-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="8b9f3-131">Matris üs öğeleri</span><span class="sxs-lookup"><span data-stu-id="8b9f3-131">Matrix Exponentials</span></span>
<span data-ttu-id="8b9f3-132">Bir [*matris üstel*](https://en.wikipedia.org/wiki/Matrix_exponential) , üstel işlevine tam benzerleme vurguladı de tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="8b9f3-133">Matris $A matris üstel $ olarak ifade edilebilir</span><span class="sxs-lookup"><span data-stu-id="8b9f3-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="8b9f3-134">$ $ e ^ A = \ cıvabitti + a + \frac{A ^ 2 } {2!} + \frac{A ^ 3 } {3!} + \ cnoktalar $ $</span><span class="sxs-lookup"><span data-stu-id="8b9f3-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="8b9f3-135">Bu önemli bir değer, hermitian matrisi için $e ^ {IB } $ $B matris için bir Unitary zaman evrimi tarafından açıklandığı için önemlidir $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="8b9f3-136">Bu nedenle, matris üsleri gerçekleştirmek, hisse alma işlemlerinin temel bir parçasıdır ve bu da bu işlemleri tanımlamak için soru-cevap yordamları sunar.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="8b9f3-137">Klasik bir bilgisayarda matris üstel değerini hesaplamak için uygulamada birçok yol vardır ve genel olarak bu tür üslü bir üstel olarak yaklaşık olarak, perıl ile bir üstel olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="8b9f3-138">Bkz [*. Cleve Moldova ve Charles Van kredisi. "Bir matrisin üstel boyutunu hesaplamak için nineon yedi yol." SıHAR incelemesi 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , ilgili zorluk hakkında daha fazla bilgi için bkz..</span><span class="sxs-lookup"><span data-stu-id="8b9f3-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="8b9f3-139">Bir matrisin üstel değerini nasıl hesapladığınızı anlamanın en kolay yolu, bu matrisin eigenvalues ve eigenvektörlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="8b9f3-140">Özellikle, yukarıda açıklanan Spectral, her hermitian veya Unitary matrisi için $A $ bir Unitary matris $U $ ve köşegen matris $D $ $A = U ^ \dağılım D U gibi bir şekilde olduğunu söylüyor $ .  UnitID özellikleri nedeniyle $A ^ 2 = U ^ \dağılım D ^ 2 U $ ve herhangi bir güç $p için benzer $ $A ^ p = u ^ \Dağılım d ^ p u $ .  Bunu, elde ettiğimiz işleç üstel işlecinin işleç tanımına değiştirir:</span><span class="sxs-lookup"><span data-stu-id="8b9f3-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="8b9f3-141">$ $ e ^ A = U ^ \dağılım \left (\cıvadone + D + \frac{D ^ 2 } {2!} + \ cnoktalar \ sağ) U = u ^ \dağılım \begin{ bmatrix } \exp (D_ {11 } ) & 0 & \cnoktalar &0 \\\\ 0 & \exp (D_ {22 } ) & \cnoktalar & 0 \\\\ \vnoktalar & \vnoktalar & \dnoktalar & \vnoktalar \\\\ 0&0 & \ cnoktalar & \exp (D_ {nn } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="8b9f3-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="8b9f3-142">Diğer bir deyişle, matrisin eigenine dönüştürmeniz durumunda $A matris $ üstel değeri, matrisin eigenlik değerlerinin normal üstel değerini hesaplama ile eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="8b9f3-143">Hisse bilgi işlem içindeki çok sayıda işlem matris üslerinin gerçekleştirilmesini içerir. Bu arada, işleç üstel özelliğinin gerçekleştirilmesini kolaylaştırmak için bir matrisin eigenliğine dönüştürülmesi, bu kılavuzda sık görülen ve bu kılavuzun ilerleyen bölümlerinde ele alınan Trour – Suzuki-Style hisse</span><span class="sxs-lookup"><span data-stu-id="8b9f3-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="8b9f3-144">Diğer bir yararlı özellik $B $ hem Unitary hem de hermitian, yani $B = b ^ {-1 } = b ^ \ dağılım $ $B ^ 2 = \ cıvabitti $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="8b9f3-145">Bu kuralı, matris üstel değerinin yukarıdaki genişlemesine uygulayarak ve $ \ cıvalanma $ ve $B $ terimlerini birlikte gruplandırarak, kimlik $x herhangi bir gerçek değer için bu değeri görebilirsiniz $ .</span><span class="sxs-lookup"><span data-stu-id="8b9f3-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="8b9f3-146">$ $e ^ {iBx } = \cıvadone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="8b9f3-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="8b9f3-147">taşıyan.</span><span class="sxs-lookup"><span data-stu-id="8b9f3-147">holds.</span></span> <span data-ttu-id="8b9f3-148">Bu işlem özellikle yararlıdır çünkü $B boyutu üstel olarak büyük olsa bile, $ $B $ hem Unitary hem de hermitian olduğu zaman özel durum için</span><span class="sxs-lookup"><span data-stu-id="8b9f3-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
