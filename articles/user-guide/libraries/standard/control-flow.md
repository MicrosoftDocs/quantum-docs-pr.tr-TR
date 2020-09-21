---
title: Q#Standart liçlerin akış denetimleri
description: Microsoft standart kitaplığı 'ndaki Flow denetim işlemleri ve işlevleri hakkında bilgi edinin Q# .
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1cfef50cf2bbecd2043972a662edd8120c5570ec
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835630"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="69991-103">Daha yüksek sıralı denetim akışı</span><span class="sxs-lookup"><span data-stu-id="69991-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="69991-104">Standart kitaplığın birincil rollerinden biri, yüksek düzey algoritmik fikirlerinin [hisse programları](https://en.wikipedia.org/wiki/Quantum_programming)olarak hızlı bir şekilde yönetilmesini kolaylaştırmaktır.</span><span class="sxs-lookup"><span data-stu-id="69991-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="69991-105">Bu nedenle, Q# Canon işlevlerin ve işlemlerin kısmi uygulaması kullanılarak uygulanan çeşitli farklı akış denetim yapıları sağlar.</span><span class="sxs-lookup"><span data-stu-id="69991-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="69991-106">Bir örneğe hemen atlamak için, bir kasada "CNOT merdiveni" oluşturmak istediği durumu düşünün:</span><span class="sxs-lookup"><span data-stu-id="69991-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="69991-107">Bu kalıbı yineleme ve döngüleri kullanarak ifade edebilirsiniz `for` :</span><span class="sxs-lookup"><span data-stu-id="69991-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="69991-108"><xref:microsoft.quantum.canon.applytoeachca>Ancak, gibi dizi işleme işlevlerinde ifade edilir, <xref:microsoft.quantum.arrays.zip> ancak bu çok daha kısadır ve okunması daha kolaydır:</span><span class="sxs-lookup"><span data-stu-id="69991-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="69991-109">Bu bölümün geri kalanında, Canon to sıkı Express hisse programları tarafından sunulan çeşitli Flow denetim işlemlerinin ve işlevlerinin nasıl kullanılacağına dair birkaç örnek sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="69991-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="69991-110">Işlemler ve Işlevleri diziler ve aralıklar üzerinde uygulama</span><span class="sxs-lookup"><span data-stu-id="69991-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="69991-111">Canon tarafından sunulan birincil soyutlamalar yinelemeden biridir.</span><span class="sxs-lookup"><span data-stu-id="69991-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="69991-112">Örneğin, tek bir-qubit Unitary $U $ için $U \otimes U \otimes \cnoktalar \otimes U $ biçiminde bir Unitary değerini düşünün.</span><span class="sxs-lookup"><span data-stu-id="69991-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="69991-113">Q#' De, <xref:microsoft.quantum.arrays.indexrange> bunu `for` bir yazmaç üzerinde döngü olarak göstermek için kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="69991-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="69991-114">Daha sonra bu yeni işlemi, `HAll(register)` $H \Otimes h \otimes \cnoktalar \otimes h $ ' a uygulamak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69991-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="69991-115">Bununla birlikte, özellikle daha büyük bir algoritmadaki bu çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="69991-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="69991-116">Üstelik, bu yaklaşım her bir qubit için uygulamak istediğimiz belirli bir işlem için özelleştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="69991-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="69991-117">Bu algoritmik kavramını daha açık bir şekilde ifade etmek için işlemlerin birinci sınıf olduğu gerçeğini kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="69991-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="69991-118">Burada sonek, `CA` çağrısının `ApplyToEach` kendi adjointable ve denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="69991-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="69991-119">Bu nedenle, `U` `Adjoint` ve destekliyorsa `Controlled` , aşağıdaki satırlar eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="69991-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="69991-120">Özellikle bu, ' `ApplyToEachCA` nin bir adjoint özelleştirmenin otomatik olarak oluşturulduğu işlemlerde görünebileceği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="69991-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="69991-121">Benzer şekilde, <xref:microsoft.quantum.canon.applytoeachindex> formun desenlerini temsil etmek için yararlıdır `U(0, targets[0]); U(1, targets[1]); ...` ve kendi girişi tarafından desteklenen her bir tek bir bileşim birleşimi için sürümler sağlar.</span><span class="sxs-lookup"><span data-stu-id="69991-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="69991-122">`ApplyToEach` tür parametreli, dışında bir girişi olan işlemlerle kullanılabilmesi için `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="69991-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="69991-123">Örneğin, `codeBlocks` kurtarılması gereken bir değer dizisi olduğunu varsayalım <xref:microsoft.quantum.errorcorrection.logicalregister> .</span><span class="sxs-lookup"><span data-stu-id="69991-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="69991-124">Ardından `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` , `code` `recoveryFn` her bloğa bağımsız olarak hata düzeltme kodu ve kurtarma işlevi uygular.</span><span class="sxs-lookup"><span data-stu-id="69991-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="69991-125">Bu, klasik girişler için bile geçerlidir: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` $ \pı/$2 yaklaşık $X $, ardından $Y $ hakkında $Pi/$3 dönüşü uygular.</span><span class="sxs-lookup"><span data-stu-id="69991-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="69991-126">Q#Canon, işlevsel programlamaya tanıdık olan klasik numaralandırma desenleri için de destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="69991-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="69991-127">Örneğin, bir <xref:microsoft.quantum.arrays.fold> \_ \_ \_ liste üzerinde bir işlevi azaltmak için $f (f (f (s {\Text{Initial}}, x 0), \noktalar) $ düzenini uygular.</span><span class="sxs-lookup"><span data-stu-id="69991-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="69991-128">Bu model toplamları, ürünleri, Minima, MAXIMA ve diğer benzeri işlevleri uygulamak için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="69991-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="69991-129">Benzer şekilde, ve gibi işlevler ' <xref:microsoft.quantum.arrays.mapped> <xref:microsoft.quantum.arrays.mappedbyindex> de fonksiyonel programlama kavramlarını ifade etmek için kullanılabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="69991-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="69991-130">Işlemleri ve Işlevleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="69991-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="69991-131">Canon tarafından sunulan denetim akışı yapıları ve işlevleri, çeşitli işlemleri veya işlevleri tek bir çağrılabilir hale getirilebilmeme yararlı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="69991-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="69991-132">Örneğin, ^ {\abger} $ $UVU deseninin son derece ortak olduğu için, Canon <xref:microsoft.quantum.canon.applywith> Bu model için bir soyutlama olarak işlem sağlar.</span><span class="sxs-lookup"><span data-stu-id="69991-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="69991-133">Bu soyutlama Ayrıca, `Controlled` sıranın üzerinde `U(qubit); V(qubit); Adjoint U(qubit);` işlem yapması gerekmiyorsa, devrelere daha etkili bir şekilde uyum sağlar `U` .</span><span class="sxs-lookup"><span data-stu-id="69991-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="69991-134">Bunu görmek için, $c (U) $ 'nin Unitary temsil `Controlled U([control], target)` ettiği ve $c (V) $ ile aynı şekilde tanımlanmasına izin verin.</span><span class="sxs-lookup"><span data-stu-id="69991-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="69991-135">Daha sonra, rastgele bir durum $ \ket{\psı} $, \begin{hizalaması} c (U) c (V) c (U) ^ \hanger \ demet {1} \otimes \ket{\psı} & = \ket {1} ^ {\abger} \ket{\psı}) \\ \\ & = (\cıvadone \otimes u) (c (V)) (\cıvadone \otimes u ^ \gesger) {1}</span><span class="sxs-lookup"><span data-stu-id="69991-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="69991-136">tanımı tarafından \end{hizalaması} `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="69991-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="69991-137">Diğer taraftan, \begin{hizalaması} c (U) c (V) c (U) ^ \dağılım \demet {0} \otimes \ket{\psı} & = \ket {0} \otimes \ket{\psı} \\ \\ & = \KET {0} \otimes (uu ^ \gesger \ket{\psı}) \\ \\ & = (\cıvadone \Otimes u) (c (V)) (\cıvado \otimes u ^ \dağılım) \demet {0} \otimes</span><span class="sxs-lookup"><span data-stu-id="69991-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="69991-138">\* End{hizalaması} bu şekilde, tüm giriş durumları için bu şekilde $U $ devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="69991-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="69991-139">Diğer bir deyişle, $c (UVU ^ \dağılım) = U c (V) U ^ \dağılım $.</span><span class="sxs-lookup"><span data-stu-id="69991-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="69991-140">Denetim işlemleri genel olarak pahalı olabildiğinden, gibi denetimli varyantlar kullanılması `WithC` ve `WithCA` uygulanması gereken denetim dütlerini azaltmaya yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="69991-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="69991-141">Düzenleme out $U $ ' ın başka bir sonucu, functor 'un nasıl uygulanacağını de bilmelidir `Controlled` `U` .</span><span class="sxs-lookup"><span data-stu-id="69991-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="69991-142">`ApplyWithCA` Bu nedenle, beklenenden daha zayıf bir imzaya sahip olabilir:</span><span class="sxs-lookup"><span data-stu-id="69991-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="69991-143">Benzer şekilde, sırayla <xref:microsoft.quantum.canon.bound> başka işlemler uygulayan işlemleri üretir.</span><span class="sxs-lookup"><span data-stu-id="69991-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="69991-144">Örneğin, aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="69991-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="69991-145">Yineleme desenleriyle birleştirmek, bunu özellikle yararlı hale getirir:</span><span class="sxs-lookup"><span data-stu-id="69991-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="69991-146">Zaman içinde sıralı bileşim</span><span class="sxs-lookup"><span data-stu-id="69991-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="69991-147">Akış denetimini kısmi uygulama ve klasik işlevler açısından düşünerek yine de ilerleyebiliriz ve klasik akış denetimi açısından oldukça karmaşık bir kavram da modelleyebilir.</span><span class="sxs-lookup"><span data-stu-id="69991-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="69991-148">Bu benzerleme vurguladı, diğer Unitary işleçleri gibi her türlü Unitary işlecinin, belirli bir Unitary işleci olarak davranacak şekilde yönergeler sunan klasik alt yordamlar için belirli bir arama dizisi oluşturma gibi, Unitary işleçlerinin yalnızca çağırma işlemlerinin yan etkilerine karşılık geldiği tanıma göre kesin hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="69991-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="69991-149">Bu görünüm altında, `Bound` tam olarak matris ürününün temsili, bu, ' `Bound([A, B])(target)` `A(target); B(target);` de $ba $ ' a karşılık gelen çağrı sırası olan öğesine denk gelir.</span><span class="sxs-lookup"><span data-stu-id="69991-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="69991-150">Daha karmaşık bir örnek, [Trour – Suzuki genişletmesi](https://arxiv.org/abs/math-ph/0506007v1).</span><span class="sxs-lookup"><span data-stu-id="69991-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="69991-151">[Veri yapılarının](xref:microsoft.quantum.libraries.data-structures)Dynamical Oluşturucu temsili bölümünde açıklandığı gibi, Trour – Suzuki genişletmesi, matris üslerini ifade etmenin özellikle faydalı bir yolunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="69991-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="69991-152">Örneğin, genişletmenin en düşük sırasıyla uygulanması $A $ ve $B $ $A = A ^ \dağılım $ ve $B = B ^ \dağılım $ gibi tüm işleçler için bunu verir. \begin{hizalaması} \tag{★} \label{EQ: Trour-Suzuki-0} \exp (i [A + B] t) = \ lim_ {n\to\infty} \left (\exp (ı/n) \exp (ı B t/n) \right) ^ n.</span><span class="sxs-lookup"><span data-stu-id="69991-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="69991-153">\end{hizalaması} birlikte, bu durum $A + B $ altında $A $ ve $B $ tek başına kapsamında gelişen bir durumu yaklaşık olarak geliştirdiğini söyler.</span><span class="sxs-lookup"><span data-stu-id="69991-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="69991-154">$A $ altında `A : (Double, Qubit[]) => Unit` $e ^ {i t A} $ uygulanan bir işlem tarafından temsil ediyorsanız,, arama dizilerini yeniden düzenleme açısından Trour – Suzuki genişletmesi gösterimi net hale gelir.</span><span class="sxs-lookup"><span data-stu-id="69991-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="69991-155">Her ne `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` kadar, ve gibi bir işlem verildiğinde `A = U(0, _, _)` `B = U(1, _, _)` , `U` form dizileri oluşturarak $t $ zaman içindeki integrali temsil eden yeni bir işlem tanımlayabiliriz</span><span class="sxs-lookup"><span data-stu-id="69991-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="69991-156">Bu noktada artık, *her şey için*ücretlendirilir – Suzuki genişletmesi olmadan bir sorun olabilir.</span><span class="sxs-lookup"><span data-stu-id="69991-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="69991-157">Genişleme, $ \eqref{EQ: Trour-Suzuki-0} $ tarafından bir çok özel yineleme düzeniyle rekabet altına alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="69991-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="69991-158">Bu yineleme deseninin uygulanma ölçütü <xref:microsoft.quantum.canon.decomposeintotimestepsca> :</span><span class="sxs-lookup"><span data-stu-id="69991-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="69991-159">' İn imzası `DecomposeIntoTimeStepsCA` , ' deki ortak bir örüntü Q# , burada, diziler tarafından desteklenen koleksiyonlar veya bir öğe, ilk öğeleri `Int` değerlerinin uzunluğunu belirten değerler olan tanımlama grupları tarafından temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="69991-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="69991-160">Birlikte yerleştirme: Işlemleri denetleme</span><span class="sxs-lookup"><span data-stu-id="69991-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="69991-161">Son olarak, Canon, `Controlled` koşullu işlem işlemlerine ek yollar sunarak, functor 'da oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="69991-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="69991-162">Özellikle de daha fazla hisse aritmetiğinde, hesaplama tabanlı durumlarda $ \ket{0\cnoktalar 0} $ dışındaki durum işlemleri için yaygın olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="69991-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="69991-163">Yukarıda tanıtılan denetim işlemlerini ve işlevleri kullanarak, tek bir bildirimde daha fazla genel hisse koşulumuz olabilir.</span><span class="sxs-lookup"><span data-stu-id="69991-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="69991-164"><xref:microsoft.quantum.canon.controlledonbitstring>Bunu nasıl yapacağım (San türü parametreler), daha sonra parçaları bir tane olacak şekilde böleceğiz.</span><span class="sxs-lookup"><span data-stu-id="69991-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="69991-165">Yapmanız gereken ilk şey, denetimi rastgele hesaplama esasına göre uygulamaya yönelik ağır bir kaldırma işlemi için gerçekten bir işlem tanımlamaktır.</span><span class="sxs-lookup"><span data-stu-id="69991-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="69991-166">Bununla birlikte, bu işlemi doğrudan çağırmayacağız. bu nedenle, `_` başka bir yapının başka bir yerde bir uygulama olduğunu göstermek için adın başına ekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="69991-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="69991-167">Sağladığımız `Bool` işleme uygulamak istediğimiz uygulamayı belirtmek için kullandığımız, dizi olarak temsil edilen bir bit dizesi sunuyoruz `oracle` .</span><span class="sxs-lookup"><span data-stu-id="69991-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="69991-168">Bu işlem doğrudan uygulamayı doğrudan yaptığından, burada olarak temsil edilen denetimi ve hedef kayıtları da ele almanız gerekir `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="69991-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="69991-169">Daha sonra, $ \ket{\vec{s}} $/$ \vec{s} $ bir bit dizesi için hesaplama tabanlı durum $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1/nokta s \_ {n-1}} $ ' ın kontrol ettiğine ilişkin bilgi</span><span class="sxs-lookup"><span data-stu-id="69991-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="69991-170">Özellikle, $ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} \ket{0\cnoktalar 0} $.</span><span class="sxs-lookup"><span data-stu-id="69991-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="69991-171">Bu $X ^ {\abger} = X $ bu yana $ \ket{0\noktalar 0} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $ anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="69991-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="69991-172">Bu nedenle, $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \cnoktalar \Otimes x ^ {s \_ {n-1}} $, uygulayabilir `Controlled oracle` ve $ \vec{s} $ dizinine geri dönüşüm uygulayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="69991-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="69991-173">Bu oluşturma işlemi tam `ApplyWith` olarak, Yeni işlediğimiz gövdesini buna göre yazdık:</span><span class="sxs-lookup"><span data-stu-id="69991-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="69991-174">Burada, ' nin <xref:microsoft.quantum.canon.applypaulifrombitstring> ile kullanım için kısmen uygulanması $P $ ' i uygulamak için kullandık `ApplyWith` .</span><span class="sxs-lookup"><span data-stu-id="69991-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="69991-175">Ancak, *Denetim* kaydını istenen formumuza dönüştürmemiz gerektiğini unutmayın. bu nedenle, hedefte iç işlemi kısmen uygulayacağız `(Controlled oracle)` . *target*</span><span class="sxs-lookup"><span data-stu-id="69991-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="69991-176">Bu, `ApplyWith` tam olarak istediğiniz gibi, denetim yazmacını $P $ ile birlikte bırakır.</span><span class="sxs-lookup"><span data-stu-id="69991-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="69991-177">Bu noktada yapılabiliriz, ancak yeni operasyonumuzın, functor uygulama gibi "uygun değil" olarak karşılanmıyor `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="69991-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="69991-178">Bu nedenle, Oracle 'ın denetlenmesi ve yeni bir işlem döndürmesi için geçen bir işlev yazarak yeni denetim akışı kavramımız tanımlamayı tamamlayacağız.</span><span class="sxs-lookup"><span data-stu-id="69991-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="69991-179">Bu şekilde, yeni işlevimiz, `Controlled` ve Canon 'yi kullanarak güçlü yeni denetim akışı yapılarını kolayca tanımlayabiliriz Q# .</span><span class="sxs-lookup"><span data-stu-id="69991-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
