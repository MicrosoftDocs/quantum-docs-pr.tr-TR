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
# <a name="vectors-and-matrices"></a><span data-ttu-id="e15bc-103">Vektörler ve matrisler</span><span class="sxs-lookup"><span data-stu-id="e15bc-103">Vectors and Matrices</span></span>

<span data-ttu-id="e15bc-104">Vektör ve matrislerle ilgili bazı benzerlik, hisse bilgi işlem anlamak için önemlidir.</span><span class="sxs-lookup"><span data-stu-id="e15bc-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="e15bc-105">Aşağıdaki kısa bir giriş sağlıyoruz ve ilgilendiğiniz okuyucular *, mg, G. (1993) gibi doğrusal algela 'da standart bir başvuruyu okumak için önerilir. Doğrusal algeköşeli giriş (Vol. 3). Kaynak listesi, MA: kaynak Lesley-Cambridge Press* veya [Doğrusal algedeniz](http://joshua.smcvt.edu/linearalgebra/)gibi bir çevrimiçi başvuru.</span><span class="sxs-lookup"><span data-stu-id="e15bc-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="e15bc-106">Boyutun (veya boyutunun) bir sütun vektörü (veya bir [*vektör*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ $n $ , bir $ sütun olarak düzenlenmiş bir $n karmaşık sayılar $ (v_1, v_2, \lnoktalar, V_n) $ koleksiyonudur:</span><span class="sxs-lookup"><span data-stu-id="e15bc-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="e15bc-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-108">v_1\\\\</span></span>
<span data-ttu-id="e15bc-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-109">v_2\\\\</span></span>
<span data-ttu-id="e15bc-110">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-110">\vdots\\\\</span></span>
<span data-ttu-id="e15bc-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="e15bc-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="e15bc-112">Vektör $v norm $ $ \sqrt { \ Sum \_ i | v \_ i | ^ 2 } $ olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="e15bc-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="e15bc-113">Bir Vector öğesinin normu $1 ise birim norm (ya da bir [*birim vektörü*](https://en.wikipedia.org/wiki/Unit_vector)olarak adlandırılır) olduğu söylenir $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="e15bc-114">[*Vector $v adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) , $ ^ \dağılım $v gösterilir $ ve $ \* $ karmaşık eşleniği ifade eden aşağıdaki satır vektörü olarak tanımlanmıştır</span><span class="sxs-lookup"><span data-stu-id="e15bc-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="e15bc-115">$ $ \begin{ bmatrix } v_1 \\ \\ \vnoktalar \\ \\ V_n \end{ bmatrix } ^ \hanger = \begin{ bmatrix } v_1 ^ \* & \cnoktalar & V_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="e15bc-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="e15bc-116">İki vektörün birlikte çarpılabilmesinin en yaygın yolu, bir nokta ürünü olarak da bilinen [*iç üründür*](https://en.wikipedia.org/wiki/Inner_product_space).</span><span class="sxs-lookup"><span data-stu-id="e15bc-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="e15bc-117">İç ürün, bir vektörün başka bir vektör için projeksiyonu sağlar ve diğer daha basit vektörler toplamı olarak bir Vector öğesinin nasıl ifade alınacağını açıklamak açısından değerlidir.</span><span class="sxs-lookup"><span data-stu-id="e15bc-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="e15bc-118">$U ve $v arasındaki iç ürün $ $ , belirtilen $ \left \langle u, v \right \rangle $ olarak tanımlanır</span><span class="sxs-lookup"><span data-stu-id="e15bc-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="e15bc-119">$ $ \langle u, v \rangle = u ^ \hanger v = u \_ 1 ^ { \* } v_1 + \cnoktalar + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="e15bc-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="e15bc-120">Bu gösterim Ayrıca bir vektör $v normın $ $ \sqrt { \langle v, v $ olarak yazılmasına izin verir \rangle } .</span><span class="sxs-lookup"><span data-stu-id="e15bc-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="e15bc-121">$Girişleri $c ile çarpıldığı yeni bir vektör oluşturmak için, bir vektörü sayı $c çarpıyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="e15bc-122">Ayrıca, $ $ girdileri $u ve $v girişlerinin toplamı olan yeni bir vektör oluşturmak için $u iki vektör de ekleyebiliriz $v $ $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="e15bc-123">Bu işlemler aşağıda gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="e15bc-123">These operations are depicted below:</span></span>

<span data-ttu-id="e15bc-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-125">u_1\\\\</span></span>
<span data-ttu-id="e15bc-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-126">u_2\\\\</span></span>
<span data-ttu-id="e15bc-127">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-127">\vdots\\\\</span></span>
<span data-ttu-id="e15bc-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-129">v_1\\\\</span></span>
    <span data-ttu-id="e15bc-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-130">v_2\\\\</span></span>
    <span data-ttu-id="e15bc-131">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-131">\vdots\\\\</span></span>
    <span data-ttu-id="e15bc-132">V_n \end{ bmatrix } , ~ \mathrm{then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="e15bc-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="e15bc-135">\ sanal noktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-135">\vdots\\\\</span></span>
<span data-ttu-id="e15bc-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e15bc-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e15bc-137">Bir boyut [*matrisi*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) $m \times n $ , $ $ $ aşağıda gösterildiği gibi $m satırlarda ve $n sütunlarında düzenlenmiş $MN karmaşık sayıların bir koleksiyonudur:</span><span class="sxs-lookup"><span data-stu-id="e15bc-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="e15bc-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-139">M_ {11 } ~ ~ m_ {12 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cnoktalar ~ ~ m_ {2n } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="e15bc-140">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cnoktalar ~ ~ m_ {MN } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="e15bc-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="e15bc-141">Boyut $n vektörünün $ yalnızca bir boyut matrisi $n \ saat 1 olduğunu unutmayın $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="e15bc-142">Vektörlerde olduğu gibi, her girdinin $c çarpıldığı yeni bir matrisi elde etmek için bir matrisi sayı $c çarpabiliriz $ $ ve girişleri iki matrisin ilgili girişlerinin toplamı olan yeni bir matris oluşturmak için aynı boyutta iki matris ekleyebiliriz.</span><span class="sxs-lookup"><span data-stu-id="e15bc-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="e15bc-143">Matris çarpma ve Tensor ürünleri</span><span class="sxs-lookup"><span data-stu-id="e15bc-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="e15bc-144">Ayrıca, boyut $ $m \times n $ ve boyutun $N boyut $n \times p ' nin iki matrisi de çarpıp $M $ $ $ $P \times p $ :</span><span class="sxs-lookup"><span data-stu-id="e15bc-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="e15bc-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-145">\begin{align}</span></span>
<span data-ttu-id="e15bc-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-147">M_ {11 } ~ ~ m_ {12 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cnoktalar ~ ~ m_ {2n } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="e15bc-148">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cnoktalar ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="e15bc-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="e15bc-149">ererbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-149">\end{bmatrix}</span></span>
<span data-ttu-id="e15bc-150">başladıbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-150">\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-151">N_ {11 } ~ ~ N_ {12 } ~ ~ \cnoktalar ~ ~ N_ {1p } \\ \\ N_ {21 } ~ ~ N_ {22 } ~ ~ \cnoktalar ~ ~ N_ {2p } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="e15bc-152">N_ {N1 } ~ ~ N_ {N2 } ~ ~ \cnoktalar ~ ~ N_ {NP}</span><span class="sxs-lookup"><span data-stu-id="e15bc-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="e15bc-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cnoktalar ~ ~ P_ {1p } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cnoktalar ~ ~ P_ {2p } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="e15bc-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cnoktalar ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="e15bc-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="e15bc-156">ererbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-156">\end{bmatrix}</span></span>
<span data-ttu-id="e15bc-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-157">\end{align}</span></span>

<span data-ttu-id="e15bc-158">$P girdileri $ $P _ {ık } = \ sum_j m_ {ij} N_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="e15bc-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="e15bc-159">Örneğin, $P _ {11 $ girdisi, ilk } $N ilk sütunuyla $M ilk satırının iç ürünüdür $ $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="e15bc-160">Vector öğesinin yalnızca bir matrisin özel durumu olduğundan, bu tanım matris-vektör çarpörüne genişletilir.</span><span class="sxs-lookup"><span data-stu-id="e15bc-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="e15bc-161">Göz önünde bulundurmanız gereken tüm matrisler, satır ve sütun sayısının eşit olduğu ve yalnızca $1 sütununa karşılık gelen vektörlerin bulunduğu kare matrisleri olacaktır $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="e15bc-162">Tek bir özel kare matrisi, [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix) $ tüm köşegen öğelerinin $1 $ ve kalan öğelerin $0 ' e eşit olması için gösterilen $ \ cıvaalı olarak belirtilen kimlik matrisi ' dir $ :</span><span class="sxs-lookup"><span data-stu-id="e15bc-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="e15bc-163">$ $ \ cıvabitti = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="e15bc-164">1 ~ ~ 0 ~ ~ \ cnoktalar ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="e15bc-165">0 ~ ~ 1 ~ ~ \ cnoktalar ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="e15bc-166">~ ~ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="e15bc-167">0 ~ ~ 0 ~ ~ \ cnoktalar ~ ~ 1 \ End{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="e15bc-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="e15bc-168">Bir kare matris $A için $ , $ $AB = ba = \ cıvaı 'nin tersi olursa matris $B [*ters*](https://en.wikipedia.org/wiki/Invertible_matrix) bir değer söyliyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="e15bc-169">Bir matrisin tersi de mevcut değildir, ancak mevcut olduğunda, bu, $A ^ {-1 $ olduğunu fark ediyoruz } .</span><span class="sxs-lookup"><span data-stu-id="e15bc-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="e15bc-170">Tüm matris $M için $ , $M adjoint veya eşleniği devrik $ bir matris $N $ $N _ {ij } = m_ {Ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="e15bc-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="e15bc-171">$M adjoint, $ genellikle ^ \ dağılım $M olarak gösterilir $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="e15bc-172">$$Uu ^ \linger = [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) u ^ \Linger U = \boldone $ veya equivalently, $U ^ {-1 } = u ^ \ dağılım $ . $U</span><span class="sxs-lookup"><span data-stu-id="e15bc-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="e15bc-173">Belki de Unitary matrislerinin en önemli özelliği, bir vektör 'nin norm düzeyini korumıdır.</span><span class="sxs-lookup"><span data-stu-id="e15bc-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="e15bc-174">Bu durum</span><span class="sxs-lookup"><span data-stu-id="e15bc-174">This happens because</span></span> 

<span data-ttu-id="e15bc-175">$ $ \langle v, v \rangle = v ^ \hanger v = v ^ \hanger U ^ {-1 } U v = v ^ \hanger u ^ \hanger u v = \langle u v, u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="e15bc-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="e15bc-176">Matris $M $ , $M = a ^ \linger Ise [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) olarak kabul edilir $ .</span><span class="sxs-lookup"><span data-stu-id="e15bc-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="e15bc-177">Son olarak, iki matrisin $M $m n ve boyutu $N boyut olan [*Tensor ürünü*](https://en.wikipedia.org/wiki/Tensor_product) (veya Kronecker ürünü), $ \times $ $ $p \times q, $P $ \otimes /saat nq boyutunda daha büyük bir dizey $MP $ $ ve $M ile elde edilir $ $ :</span><span class="sxs-lookup"><span data-stu-id="e15bc-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="e15bc-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-178">\begin{align}</span></span>
    <span data-ttu-id="e15bc-179">K \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-180">M_ {11 } ~ ~ \cnoktalar ~ ~ m_ {1n } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="e15bc-181">M_ {M1 } ~ ~ \cnoktalar ~ ~ m_ {MN}</span><span class="sxs-lookup"><span data-stu-id="e15bc-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="e15bc-182">ererbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-182">\end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-184">N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="e15bc-185">N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ}</span><span class="sxs-lookup"><span data-stu-id="e15bc-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="e15bc-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-187">M_ {11 } \begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \ End{ bmatrix } ~ ~ \cnoktalar ~ ~ m_ {1n } \begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{ bmatrix } \\ \\ \dnoktalar\\\\</span><span class="sxs-lookup"><span data-stu-id="e15bc-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="e15bc-188">M_ {M1 } \ Begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{ bmatrix } ~ ~ \cnoktalar ~ ~ m_ {MN } \ Begin{ bmatrix } N_ {11 } ~ ~ \cnoktalar ~ ~ N_ {1Q } \\ \\ \ dnoktalar \\\\ N_ {P1 } ~ ~ \cnoktalar ~ ~ N_ {PQ } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e15bc-189">\end{bmatrix}.</span></span>
<span data-ttu-id="e15bc-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-190">\end{align}</span></span>

<span data-ttu-id="e15bc-191">Bu, bazı örneklerde daha iyi gösterilmiştir:</span><span class="sxs-lookup"><span data-stu-id="e15bc-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="e15bc-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \ End{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-194">\begin{ bmatrix } c \\ \\ d \\ \\ e \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="e15bc-195">\\\\[1,5 em] b \ Begin{ bmatrix } c \\ \\ d \\ \\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-196">ererbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-196">\end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-197">= \begin{ bmatrix } a c \\ \\ a d \\ \\ a \\ \\ b c \\ \\ b d \\ \\ s\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="e15bc-198">ve</span><span class="sxs-lookup"><span data-stu-id="e15bc-198">and</span></span>

<span data-ttu-id="e15bc-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="e15bc-202">e \ f \\ \\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="e15bc-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-204">a\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-205">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-206">kenarı\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-207">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-208">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-209">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-210">TID\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-211">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-212">ererbmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-212">\end{bmatrix}</span></span>
    <span data-ttu-id="e15bc-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="e15bc-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="e15bc-214">AE \ AF \ be \ BF \\ \\ AG \ Ah \ bg \ BH \\ \\ CE \ CF \ de \ df \\ \\ CG \ ch \ DG \ DH \ End{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="e15bc-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="e15bc-215">Tencursor ürünlerini çevreleyen son yararlı bir notational kuralı, her bir vektör $v $ veya matris $M için $ $v ^ {\otimes n } $ veya $M ^ {\otimes n $ 'ın } $n $ katlamalı bir yinelenen Tensor ürünü için kısa bir seçenektir.</span><span class="sxs-lookup"><span data-stu-id="e15bc-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="e15bc-216">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="e15bc-216">For example:</span></span>

<span data-ttu-id="e15bc-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-217">\begin{align}</span></span>
<span data-ttu-id="e15bc-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{1 0 bmatrix } \\ \\ \end{ bmatrix } , \qdörtlü \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qdörtlü \begin{bmatrix} 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ 1 \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 1 0 \\ \\ & \ End{ bmatrix } , \qdörtlü \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0 \\ \\ \\ \\ \\\\ \end{bmatrix}&0&1 &0&0&1 &0&0&0 &</span><span class="sxs-lookup"><span data-stu-id="e15bc-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="e15bc-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e15bc-219">\end{align}</span></span>
