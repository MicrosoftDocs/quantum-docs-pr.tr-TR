---
title: Pauli ölçümleri
description: Tek ve Multi-qubit Pauli ölçüm işlemleriyle nasıl çalışacağınızı öğrenin.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
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
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269482"
---
# <a name="pauli-measurements"></a><span data-ttu-id="b752a-103">Pauli ölçümleri</span><span class="sxs-lookup"><span data-stu-id="b752a-103">Pauli Measurements</span></span>

<span data-ttu-id="b752a-104">Önceki tartışmalarda hesaplama tabanlı ölçümlere odaklandık.</span><span class="sxs-lookup"><span data-stu-id="b752a-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="b752a-105">Aslında, notational perspektifinden, işlem tabanlı ölçümlerde hızlı bir şekilde ifade etmek için uygun olan, hisse kullanımı açısından oluşan diğer yaygın ölçümler vardır.</span><span class="sxs-lookup"><span data-stu-id="b752a-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="b752a-106">Q # ile çalışırken, çalıştıracağınız en yaygın ölçüm türleri *Pauli ölçümleri*olacaktır, bu da diğer tabanlarda ölçümleri dahil etmek için hesaplama tabanlı ölçümleri genelleştirir ve farklı qugeler arasında eşlik sağlar.</span><span class="sxs-lookup"><span data-stu-id="b752a-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="b752a-107">Bu gibi durumlarda, bir Pauli işlecinin, genel olarak $X, Y, Z $ veya $Z \otimes Z, x \otimes x, x Y vb. gibi bir operatör \otimes $ ölçmesi konusunda tartışmak yaygındır.</span><span class="sxs-lookup"><span data-stu-id="b752a-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="b752a-108">Q # içinde, Multi-qubit Pauli işleçleri genellikle türündeki diziler tarafından temsil edilir `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="b752a-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="b752a-109">Örneğin, $X \otimes Y. i 'yi göstermek için $ , diziyi kullanabilirsiniz `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="b752a-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="b752a-110">Pauli işleçleri açısından ölçüm ele alınması, özellikle de hisse hata düzeltmesinin alt alanında ortaktır.</span><span class="sxs-lookup"><span data-stu-id="b752a-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="b752a-111">Q # ' da benzer bir kuralı izliyoruz; Artık ölçümlerin bu alternatif görünümünü açıkladık.</span><span class="sxs-lookup"><span data-stu-id="b752a-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="b752a-112">Pauli ölçüsünün nasıl düşündüğünün ayrıntılarına geçmeden önce, hisse bir bilgisayar içinde tek bir qubit 'in ne ölçmeye yönelik olduğunu düşünmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="b752a-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="b752a-113">$N $ -qubit hisse anımız olduğunu düşünün; ardından bir qubit, durumun içinde olabilecek $2 ^ n $ olasılıklarının yarısını hemen ölçmelidir.</span><span class="sxs-lookup"><span data-stu-id="b752a-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="b752a-114">Diğer bir deyişle, ölçüm, hisse durumunu iki yarım boşluktan birine göre projeler.</span><span class="sxs-lookup"><span data-stu-id="b752a-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="b752a-115">Bu ıntut 'i yansıtmak için ölçüm hakkında düşündüğünüzden bahsede genelleştireceğiz.</span><span class="sxs-lookup"><span data-stu-id="b752a-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="b752a-116">Bu alt boşlukların öz belirlemek için, bunları açıklamak için bir dile ihtiyacımız var.</span><span class="sxs-lookup"><span data-stu-id="b752a-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="b752a-117">İki alt boşluğu tanımlamanın bir yolu, kural tarafından $ \pm 1 olacak şekilde yalnızca iki benzersiz eigenvalues içeren bir matrisi belirtmektir $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="b752a-118">Alt boşlukları bu şekilde açıklayan basit bir örnek için $Z göz önünde bulundurun $ :</span><span class="sxs-lookup"><span data-stu-id="b752a-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="b752a-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-119">$$ \begin{align}</span></span>
  <span data-ttu-id="b752a-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \ End{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="b752a-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="b752a-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-121">\end{align}</span></span>
$$

<span data-ttu-id="b752a-122">Pauli-$Z matrisinin köşegen öğelerini okuyarak, " $ $ } } karşılık gelen eigenvalues $ \pm 1 ile birlikte iki eigenvektörün, $ \ket{0 $ ve $ \ket{1 $ $Z olduğunu görebiliriz $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="b752a-123">Bu nedenle, qubit ' i ölçyoruz ve elde ediyorsanız `Zero` ($ \ket{0 $ durumuna karşılık gelir } ), qubitin durumunun $Z işlecinin $ + 1 $ eigenstate olduğunu biliyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="b752a-124">Benzer şekilde, elde etmemiz durumunda `One` , qubitimizin durumunun bir $-1 $ eigenstate $Z olduğunu biliyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="b752a-125">Bu işlem, Pauli ölçümlerinin dilinde "ölçüm Pauli $Z" olarak adlandırılır $ ve hesaplama tabanlı ölçüm gerçekleştirmeye tamamen eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="b752a-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="b752a-126">\times $ $Z bir Unitary dönüştürmesi olan $2 2 matrisi $ de bu ölçütleri karşılar.</span><span class="sxs-lookup"><span data-stu-id="b752a-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="b752a-127">Diğer bir deyişle, $ $ $ \pm 1 eigenvektörlerinde bir ölçünün iki sonucunu tanımlayan bir matris vermek için $U başka bir Unitary Z u olan matris $A de kullanabiliriz $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="b752a-128">Pauli ölçülerinin gösterimi, $X, Y, Z $ ölçümlerini bir qubitden bilgi elde etmek için yaptığı eşdeğer ölçümler olarak tanımlayarak bu Unitary denklik 'e başvurur.</span><span class="sxs-lookup"><span data-stu-id="b752a-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="b752a-129">Bu ölçümler, kolaylık sağlamak için aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b752a-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="b752a-130">Pauli ölçümü</span><span class="sxs-lookup"><span data-stu-id="b752a-130">Pauli Measurement</span></span>  |<span data-ttu-id="b752a-131">Unitary dönüştürmesi</span><span class="sxs-lookup"><span data-stu-id="b752a-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="b752a-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="b752a-132">$Z$</span></span>               | <span data-ttu-id="b752a-133">$ \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-133">$\boldone$</span></span>             |
| <span data-ttu-id="b752a-134">$X$</span><span class="sxs-lookup"><span data-stu-id="b752a-134">$X$</span></span>               | <span data-ttu-id="b752a-135">$H$</span><span class="sxs-lookup"><span data-stu-id="b752a-135">$H$</span></span>                    |
| <span data-ttu-id="b752a-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="b752a-136">$Y$</span></span>               | <span data-ttu-id="b752a-137">$HS ^ {\dağılım}$</span><span class="sxs-lookup"><span data-stu-id="b752a-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="b752a-138">Diğer bir deyişle, bu dil kullanıldığında, "Measure $Y $ ", ^ \linger $HS uygulama $ ve sonra hesaplama temelinde ölçme ile eşdeğerdir; burada, [`S`](xref:microsoft.quantum.intrinsic.s) bazen "aşama kapısı" olarak adlandırılan ve Unitary matrisi tarafından benzetilen bir iç hisse dır</span><span class="sxs-lookup"><span data-stu-id="b752a-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="b752a-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-139">$$ \begin{align}</span></span>
    <span data-ttu-id="b752a-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="b752a-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="b752a-141">1 & 0 \\ \\ 0 & ı \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="b752a-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="b752a-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-142">\end{align}</span></span>
$$

<span data-ttu-id="b752a-143">Ayrıca, hisse için $HS ^ \dağılım $ $Z ve sonra da $ aşağıdaki işlem ile eşdeğer olacak şekilde ölçkla eşdeğerdir `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="b752a-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="b752a-144">Doğru durum daha sonra hesaplama temeline geri dönüşümle, bu da hisse $SH. $ Yukarıdaki kod parçacığında, işlem temelinde yapılan dönüşüm, blok kullanılarak otomatik olarak işlenir `within … apply` .</span><span class="sxs-lookup"><span data-stu-id="b752a-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="b752a-145">Q # ' da, sonuç---, durum---ile etkileşimde bulunarak ayıklanan klasik bilgiler, `Result` \\ } } \\ sonucun Pauli işlecinin $ (-1) ^ j eigenin ' de olup olmadığını belirten bir değer olan $j \In {\Texttt{Zero, \Texttt{One} $ değeri tarafından verilir $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="b752a-146">Birden çok qubit ölçümleri</span><span class="sxs-lookup"><span data-stu-id="b752a-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="b752a-147">Multi-qubitpauli işleçlerinin ölçümleri benzer şekilde, şöyle görüldüğü gibi tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="b752a-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="b752a-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1 \\\\ \end{bmatrix}&0&0&1.</span><span class="sxs-lookup"><span data-stu-id="b752a-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="b752a-149">Bu nedenle, iki Pauli-$Z işleçlerinin Tensor ürünleri, $ $ + 1 $ ve $-1 eigenvalues içeren iki boşluktan oluşan bir matris oluşturur $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="b752a-150">Tek qubit durumunda olduğu gibi, her ikisi de erişilebilir vektör alanının yarısını $ + 1 $ eigenspace ve $-1 eigenspace 'e ait olan yarı boşluk anlamına gelir $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="b752a-151">Genel olarak, Pauli-$Z işleçlerinin herhangi bir tencursor ürünüyle $ ve kimliğin buna uda ulaşana kadar, Tensor ürünü tanımından kolayca bakmak kolaydır.</span><span class="sxs-lookup"><span data-stu-id="b752a-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="b752a-152">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="b752a-152">For example,</span></span>

<span data-ttu-id="b752a-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-153">$$ \begin{align}</span></span>
    <span data-ttu-id="b752a-154">Z \otimes \cıvadone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="b752a-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="b752a-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 0 & 0 \\ \\ & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="b752a-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="b752a-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-156">\end{align}</span></span>
$$

<span data-ttu-id="b752a-157">Daha önce olduğu gibi, bu tür Matrislerin her türlü Unitary dönüştürmesi, $ \pm 1 eigenvalues ile etiketlenmiş iki yarı boşluğu da açıklar $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="b752a-158">Örneğin, $X \otimes X = H \otimes h (z \otimes z) h h, \otimes $ $Z = HXH olan kimlikten $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="b752a-159">Tek qubit durumuna benzer şekilde, tüm iki-qubit Pauli-ölçümleri, \otimes $ $4 \times 4 $ unitary $U için $U ^ \dağılım (Z \ID) U olarak yazılabilir $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="b752a-160">Aşağıdaki tablodaki dönüşümleri numaralandırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="b752a-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="b752a-161">Aşağıdaki tabloda, $ } $ \begin{align matrisini göstermek için $ \operatorname{Swap $ kullanıyoruz}</span><span class="sxs-lookup"><span data-stu-id="b752a-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="b752a-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="b752a-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="b752a-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \ End{Matrix } \ right) \end{ALIGN}</span><span class="sxs-lookup"><span data-stu-id="b752a-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="b752a-164">$ $ iç işlemin benzetimini yapmak için kullanılır [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="b752a-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="b752a-165">Pauli ölçümü</span><span class="sxs-lookup"><span data-stu-id="b752a-165">Pauli Measurement</span></span>     |<span data-ttu-id="b752a-166">Unitary dönüştürmesi</span><span class="sxs-lookup"><span data-stu-id="b752a-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="b752a-167">$Z \otimes \ bolbitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="b752a-168">$ \ cıvalanma \otimes \cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="b752a-169">$Z \otimes \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="b752a-170">$ \ cıvabitti \otimes \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="b752a-171">$X \otimes \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="b752a-172">$H \otimes \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="b752a-173">$Y \otimes \ cıvabitti$</span><span class="sxs-lookup"><span data-stu-id="b752a-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="b752a-174">$HS ^ \dağılım \otimes \ cıvataleti$</span><span class="sxs-lookup"><span data-stu-id="b752a-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="b752a-175">$ \ cıvabitti \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="b752a-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="b752a-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="b752a-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b752a-177">$ \ cıvabitti \otimes X$</span><span class="sxs-lookup"><span data-stu-id="b752a-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="b752a-178">$ (H \otimes \ cıvabitti) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="b752a-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b752a-179">$ \ bolbitti \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="b752a-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="b752a-180">$ (HS ^ \dağılım \otimes \ cıvabitti) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="b752a-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="b752a-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="b752a-181">$Z\otimes Z$</span></span> | <span data-ttu-id="b752a-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="b752a-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="b752a-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="b752a-183">$X\otimes Z$</span></span> | <span data-ttu-id="b752a-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \ cıvabitti) $</span><span class="sxs-lookup"><span data-stu-id="b752a-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="b752a-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="b752a-185">$Y\otimes Z$</span></span> | <span data-ttu-id="b752a-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dağılım \otimes \ cıvabitti) $</span><span class="sxs-lookup"><span data-stu-id="b752a-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="b752a-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="b752a-187">$Z\otimes X$</span></span> | <span data-ttu-id="b752a-188">$ \operatorname{CNOT } \_ {10 } (\ cıvabitti \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="b752a-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="b752a-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="b752a-189">$X\otimes X$</span></span> | <span data-ttu-id="b752a-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="b752a-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="b752a-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="b752a-191">$Y\otimes X$</span></span> | <span data-ttu-id="b752a-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \Hanger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="b752a-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="b752a-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="b752a-193">$Z\otimes Y$</span></span> | <span data-ttu-id="b752a-194">$ \operatorname{CNOT } \_ {10 } (\ cıvabitti \otimes HS ^ \ dağılım) $</span><span class="sxs-lookup"><span data-stu-id="b752a-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="b752a-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="b752a-195">$X\otimes Y$</span></span> | <span data-ttu-id="b752a-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \ dağılım) $</span><span class="sxs-lookup"><span data-stu-id="b752a-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="b752a-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="b752a-197">$Y\otimes Y$</span></span> | <span data-ttu-id="b752a-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dağılım \otimes HS ^ \ dağılım) $</span><span class="sxs-lookup"><span data-stu-id="b752a-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="b752a-199">Burada, [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) işlem aşağıdaki nedenlerden dolayı görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="b752a-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="b752a-200">$ \Cıvadone matrisini içermeyen her Pauli ölçümü, $ \otimes Yukarıdaki düşünyana $Z Z 'ye kadar bir Unitary 'e eşittir $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="b752a-201">$Z Z 'nin eigenvalues \otimes değeri $ yalnızca her bir hesaplama tabanlı vektörü oluşturan qubits 'e bağlıdır ve denetlenen işlemler bu eşliği hesaplamak ve ilk bit içinde saklamak için işlem yapar.</span><span class="sxs-lookup"><span data-stu-id="b752a-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="b752a-202">İlk bit ölçülene kadar, elde edilen yarı alanın kimliğini kurtararak Pauli işlecinin ölçülesiyle eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="b752a-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="b752a-203">Bir ek notta: $Z Z ölçüyü, \otimes $ ardışık olarak $Z \otimes \mathbb{1 } $ ve sonra $ \mathbb{1 \otimes Z ile aynı olduğunu varsaymaya rağmen } $ Bu varsayım yanlış olur.</span><span class="sxs-lookup"><span data-stu-id="b752a-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="b752a-204">Bunun nedeni, $Z \otimes Z $ 'yi Bu işleçlerin $ + 1 $ veya $-1 $ eigenstate ' i ile aynı şekilde ölçmeye yönelik bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="b752a-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="b752a-205">$Z \otimes \mathbb{1 } $ ve sonra $ \mathbb{1 } \otimes z $ , ilk başta $Z \mathbb{1 $ bir yarı alana \otimes } ve sonra da $ \mathbb{1 } \otimes z 'nin bir yarı alanına kadar hisse $ Dört hesaplama tabanlı vektör olduğu için, her iki ölçüm de durum, durumu çeyrek boşluk olarak azaltır ve bu nedenle tek bir hesaplama tabanlı vektöre düşürür.</span><span class="sxs-lookup"><span data-stu-id="b752a-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="b752a-206">Qubits arasında correlations</span><span class="sxs-lookup"><span data-stu-id="b752a-206">Correlations between qubits</span></span>
<span data-ttu-id="b752a-207">$X X veya $Z Z gibi Pauli matrislerinin tencursor ürünlerini ölçmeye yönelik başka bir yöntem \otimes $ \otimes $ de, bu ölçümlerin iki qubit arasındaki eş ilişkilerdeki bilgilere bakmasına olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="b752a-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="b752a-208">Ölçüm $X \otimes \ID $ , ilk qubit içinde yerel olarak saklanan bilgilere bakmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="b752a-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="b752a-209">Her iki ölçüm türü de hisse bilgi işlem ortamında eşit olmakla birlikte, önceki bir deyişle hisse bilgi işlem gücünü güçlendirin.</span><span class="sxs-lookup"><span data-stu-id="b752a-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="b752a-210">Bu, bilgi işlem ortamında, genellikle öğrenmek istediğiniz bilgilerin herhangi bir tek qubit içinde depolanmadığını, ancak aynı anda tüm qubits 'de yerel olarak depolanmadığını ve bu bilgileri yalnızca bir eklem ölçümü (örn. $Z \otimes Z) aracılığıyla arayarak $ Bu bilgilerin bildirim haline gelmesini gösterir.</span><span class="sxs-lookup"><span data-stu-id="b752a-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="b752a-211">Örneğin, hata düzeltilirken, korumamıza çalıştığımız durum hakkında hiçbir şey öğrenirken bir hata oluştuğunu öğrenmek istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="b752a-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="b752a-212">[Bit-çevir kod örneği](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) , $Z \otimes z \otimes \ID $ ve $ \ ID \otimes $ z</span><span class="sxs-lookup"><span data-stu-id="b752a-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="b752a-213">$X \otimes Y \Otimes Z \otimes \cıvadone gibi rastgele Pauli işleçleri $ de ölçülebilir.</span><span class="sxs-lookup"><span data-stu-id="b752a-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="b752a-214">Pauli işleçlerinin tüm tencursor ürünlerinin her biri yalnızca iki eigenvalues $ \pm 1 $ ve her iki eigenon, vektör alanının tamamının yarı alanlarını oluşturur.</span><span class="sxs-lookup"><span data-stu-id="b752a-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="b752a-215">Bu nedenle, yukarıda belirtilen gereksinimlere başvurırlar.</span><span class="sxs-lookup"><span data-stu-id="b752a-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="b752a-216">Q # içinde, $ ölçüm, işaret $ (-1) ^ j olan egenspace 'te bir sonuç alıyorsa, bu tür ölçümler $j döndürür $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="b752a-217">Bu tür işleçler, diagonalizing $ $ ve $ \ıd $Z 'nin bir Tensor ürünü olarak, işlemi ifade etmek için gereken $U geçidini açıklamaya yönelik, denetimli olmayan kapıları ve temel Dönüştürmelere yönelik bir yerleşik özellik olarak, Pauli ölçümleri olması yararlı olacaktır $ . Önceden tanımlanmış Bu ölçülerden birini yapmak istediğinizi belirleyebilmeksizin, bir hesaplama tabanlı ölçüm için gerekli bilgileri sağlamak üzere temelinizi nasıl dönüştürebileceğinizi merak etmeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="b752a-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="b752a-218">S #, sizin için gerekli tüm temel dönüştürmeleri otomatik olarak işler.</span><span class="sxs-lookup"><span data-stu-id="b752a-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="b752a-219">Daha fazla bilgi için bkz [`Measure`](xref:microsoft.quantum.intrinsic.measure) . ve [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) işlemleri.</span><span class="sxs-lookup"><span data-stu-id="b752a-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="b752a-220">Kopyalama olmayan bu Üyeler</span><span class="sxs-lookup"><span data-stu-id="b752a-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="b752a-221">Hisse bilgileri güçlüdür.</span><span class="sxs-lookup"><span data-stu-id="b752a-221">Quantum information is powerful.</span></span>
<span data-ttu-id="b752a-222">Faktör numaraları gibi harika şeyleri en iyi bilinen klasik algoritmalardan daha hızlı bir şekilde gerçekleştirebilmemizi veya düzgün bir şekilde benzetilmesini sağlayan bağıntılı elektron sistemlerinin verimli bir şekilde benzetimini yapmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="b752a-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="b752a-223">Ancak, hisse bilgi işlem gücüyle ilgili sınırlamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="b752a-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="b752a-224">Bu tür bir sınırlama, *hiçbir kopyalama olmayan kopya*tarafından verilir.</span><span class="sxs-lookup"><span data-stu-id="b752a-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="b752a-225">Kopyalama yok, hiçbir şekilde adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="b752a-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="b752a-226">Genel hisse durumlarının bir hisse bilgisayar tarafından kopyalanmasına izin vermez.</span><span class="sxs-lookup"><span data-stu-id="b752a-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="b752a-227">Bunların kanıtı, genel olarak basittir.</span><span class="sxs-lookup"><span data-stu-id="b752a-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="b752a-228">Bu konu başlığı altındaki bir çok teknik olmadığından, bu durum, hiçbir ek yardımcı qubit, kapsamımızda (bir hesaplama sırasında boş alan için kullanılan ve kolayca kullanıldığından ve Q # ' da yönetilir, bkz. [ödünç alınan qubit](xref:microsoft.quantum.guide.qubits#borrowed-qubits)) için çok fazla teknik değildir.</span><span class="sxs-lookup"><span data-stu-id="b752a-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="b752a-229">Bu tür bir hisse bilgisayar için kopyalama işlemi bir Unitary matrisi tarafından açıklanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b752a-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="b752a-230">Klonlamamız denendiğimiz hisse TI durumunu bozduğundan ölçüme izin vermeiyoruz.</span><span class="sxs-lookup"><span data-stu-id="b752a-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="b752a-231">Kopyalama işleminin benzetimini yapmak için, Unitary matrisinin $ $ U \ ayraç \ { PSI } \ket{0 } = \ demet { \ PSI } \ demet { \ PSI özelliğine sahip olması için kullanılmasını istiyoruz}</span><span class="sxs-lookup"><span data-stu-id="b752a-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="b752a-232">$ $ herhangi bir durum için $ $ { \psı } $.</span><span class="sxs-lookup"><span data-stu-id="b752a-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="b752a-233">Matris çarpın doğrululululu daha sonra tüm ikinci hisse için $ { \tus\phi } $,</span><span class="sxs-lookup"><span data-stu-id="b752a-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="b752a-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-234">$$ \begin{align}</span></span>
    <span data-ttu-id="b752a-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ayraç { \ Fi } + \ ayraç { \ PSI } \ right) \ right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="b752a-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="b752a-236">& = \frac{1 } {\sqrt{2 } } U \ket { } \ph\ket{0}</span><span class="sxs-lookup"><span data-stu-id="b752a-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="b752a-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psı } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \ Fi } \ { } { } {}</span><span class="sxs-lookup"><span data-stu-id="b752a-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="b752a-238">\right) \\ \\ & \a \left (\frac{1 } {\sqrt{2 } } \left ( { \tus\fi } + { \tus\psı } \ right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left ( { \tus\phi } + { \tus\psı } \ right) \ right).</span><span class="sxs-lookup"><span data-stu-id="b752a-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="b752a-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="b752a-239">\end{align}</span></span>
$$

<span data-ttu-id="b752a-240">Bu, kopya olmaması gereken temel ıntutiye sahiptir: bilinmeyen bir hisse lık durumunu kopyalayan tüm cihazlar, kopyalayan durumların en az bir kısmında yer almalıdır.</span><span class="sxs-lookup"><span data-stu-id="b752a-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="b752a-241">Cloner 'ın giriş durumunda herhangi bir şekilde hareket ederken, bu durum yardımcı qubits 'in eklenmesi ve ölçümü aracılığıyla ihlal edilebilir, ancak bu tür etkileşimler Ayrıca sistem hakkında ölçüm istatistikleri üzerinden bilgi sızıntısına ve bu gibi durumlarda tam kopyalamayı önler.</span><span class="sxs-lookup"><span data-stu-id="b752a-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="b752a-242">Daha fazla [bilgi için](xref:microsoft.quantum.more-information), kopyalamanın olmaması için daha kapsamlı bir kanıt için bkz..</span><span class="sxs-lookup"><span data-stu-id="b752a-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="b752a-243">Hisse uygun olmayan bir şekilde büyük ölçüde bir şekilde klonlamanız için, parça olmayan bir bilgi işlem için önemli değildir. bu nedenle, hisse durumlarından daha fazla bilgi edinebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b752a-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="b752a-244">Aslında, Heısenberg 'nin vaunbelirsizlik ilkesini ihlal edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b752a-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="b752a-245">Alternatif olarak, bir karmaşık hisse dağılımla tek bir örnek almak ve yalnızca bir örnekten bu dağıtım hakkında bilgi edinmek istediğiniz her şeyi öğrenmek için en uygun bir Cloner kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b752a-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="b752a-246">Bu, bir para ve gözbaşları ters çevirmiş ve sonra yanıt vermeye yönelik bir arkadaşla karşılaşmanız durumunda, "Ah 'nin dağılımı $p = 0.512643 \ lnoktalar!" ile Bernoulli olmalıdır. $</span><span class="sxs-lookup"><span data-stu-id="b752a-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="b752a-247">Bu tür bir ifade, bir veya daha fazla bilgi olmadan dağıtımı kodlamak için gereken pek çok bilgi sağlamadığı için sensik olmayan bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="b752a-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="b752a-248">Benzer şekilde, önceki bilgiler olmadan, bu tür kodların bir kısmını $p bilmeden hazırlayamazmız gibi, bir hisse bilgisini kusursuz bir şekilde klonlayamıyoruz $ .</span><span class="sxs-lookup"><span data-stu-id="b752a-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="b752a-249">Bilgiler hisse bilgi işlem ortamında ücretsizdir.</span><span class="sxs-lookup"><span data-stu-id="b752a-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="b752a-250">Ölçülen her bir qubit, tek bir bilgi verir ve kopyalama olmaması durumunda, sistem hakkında elde edilen bilgiler ve üzerinde çağrılan saldırgan arasındaki temel zorunluluğunu getirir etrafında elde etmek için kullanılabilecek bir biriktirme listesi olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="b752a-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
