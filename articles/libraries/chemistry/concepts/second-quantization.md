---
title: İkinci Quantileştirme | Microsoft Docs
description: İkinci Quantileştirme kavramsal belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
ms.openlocfilehash: b3cc7eb8139d2df6e02de371ccf7a423e58ea76d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210412"
---
# <a name="second-quantization"></a><span data-ttu-id="63fd8-103">İkinci Quantitleştirme</span><span class="sxs-lookup"><span data-stu-id="63fd8-103">Second Quantization</span></span>

<span data-ttu-id="63fd8-104">İkinci quantileştirme, farklı bir lens aracılığıyla elektronik yapı sorununa bakar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="63fd8-105">$N _E $ elektriklerinin her birini belirli bir duruma (veya orbte) atamak yerine, ikinci bir ölçü her ikisi de izler ve bunların her birinde mevcut bir elektron olup olmadığını ve aynı zamanda otomatik olarak ' nin simetri özelliklerini karşılık gelen Wave işlevi.</span><span class="sxs-lookup"><span data-stu-id="63fd8-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="63fd8-106">Bu önemli bir durumdur çünkü, giriş durumunu simetrik hale getirme (fermıons için gereklidir) ve ayrıca ikinci bir satışın bu tür modellerin küçük hisse kullanımı ile simülasyonu yapmasına izin verdiği için, tchemistry modellerinin belirtilmesiyle bilgisayarlar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="63fd8-107">İkinci bir ölçü işleme örneği olarak $ \psi_0\cnoktalara \Psı_{n-1} $ öğesinin bir orthonormal uzamsal Orbitals olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="63fd8-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="63fd8-108">Bu Orbitals, sistemi kabul edilen sonlu bir küme içinde mümkün olduğunca doğru şekilde temsil edecek şekilde seçilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="63fd8-109">Bu tür yörüntünlerde yaygın bir örnek, Hydrogen atom için bir egensiz oluşturan atomik orbitünlerdir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="63fd8-110">Elektriler iki döngü durumuna sahip olduğundan, bu tür uzamsal orbiye her biri için iki elektriklarca bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="63fd8-111">Yani, geçerli temel durumlar $ \psı_{0, \upoklu} biçimindedir, \lnoktalara, \Psı_{n-1, \upok}, \psı_{0, \downarrow}, \lnoktalar, \Psı_{n-1, \downokı} $ burada $ \uparrow $ ve $ \downok $, döndürme derecesindeki iki eigenstates belirten etiketlerdir serbestlik.</span><span class="sxs-lookup"><span data-stu-id="63fd8-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="63fd8-112">$ \Sigma \in \{\upok için $ (j, \sigma) $ öğesinin bu Birleşik dizininde, \downok\}$, hem uzamsal hem de döngü derecesi olarak depolandığı için bir döndürme-orblik olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="63fd8-113">Kimya kitaplığında, döndürme-Orbitals `SpinOrbital` veri yapısında depolanır ve aşağıdaki gibi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="63fd8-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="63fd8-114">Bu, her bir indisin bir $ (j, \sigma) $ numaralandırması olduğu için, yalnızca dalga işlevinin hem dönüş hem de uzamsal bölümünün temelini $ \psı_{0} \cnoktalarla \psi_{2N-1} $ olarak düşünebileceğimizi gösterir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="63fd8-115">Olası bir numaralandırma $g (j, \sigma) = j + N\sigma ' $.</span><span class="sxs-lookup"><span data-stu-id="63fd8-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="63fd8-116">Başka bir olası numaralandırma $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="63fd8-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="63fd8-117">Hisse dili Mistry kitaplığı bu kuralları kullanabilir ve bu tür bir kodlamada bulunan döndürme-Orbitals aşağıdaki gibi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="63fd8-118">Fermıonic sistemleri için Pauli dışlama ilkesi, aynı anda herhangi bir döndürme/zaman için birden fazla elektron 'in bulunmasını engeller.</span><span class="sxs-lookup"><span data-stu-id="63fd8-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="63fd8-119">Bu, $ \psi_1 $ olarak \begin{Equation} \psı_1 \ettarrow \begin{Cases} \tus{0}_1 & \Text{, $ \psı_1 $ boş değilse,} </span><span class="sxs-lookup"><span data-stu-id="63fd8-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="63fd8-120">\ket{1}_1 & \Text{If $ \psı_1 $ dolu.}</span><span class="sxs-lookup"><span data-stu-id="63fd8-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="63fd8-121">\end{Cases} \end{Equation} bu kodlama, farklı bir ücret bit olarak elektronik meslek depolayabileceği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="63fd8-122">$2N $ $ $ $ $ $ $ $ $ $ $ $ $ $ $/bit</span><span class="sxs-lookup"><span data-stu-id="63fd8-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="63fd8-123">Örnek olarak, $N = $2 sonra durum $ $ \ayraç{0} \tus{1} \demet{1} \demet{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="63fd8-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="63fd8-124">döndürme Orbitals $1 $ ve $2 $, kalan boş ile birlikte yer alar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="63fd8-125">Benzer şekilde, $ $ \demet{0} \equıv \tus{0} _{0} \cnoktalar \demet{0}_ {N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="63fd8-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="63fd8-126">, elektriksiz değildir ve ' vakum State ' olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="63fd8-127">İkinci bir sağlığa yönelik güzel bir yan etkisi, artık hisse durumunun simetriyi açıkça takip etmemiz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="63fd8-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="63fd8-128">Bunun nedeni, yaptığımız gibi, bir döndürme/atma 'un elektronik mesleklerini oluşturan ve yok eden operatörlerin commutation kuralları aracılığıyla bunun yerine durumunun kendisini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="63fd8-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="63fd8-129">Fermıonic işleçleri</span><span class="sxs-lookup"><span data-stu-id="63fd8-129">Fermionic operators</span></span>

<span data-ttu-id="63fd8-130">İkinci Satışlara dayalı vektörlere uygulanan iki temel operatör, oluşturma ve Ayla ilgili işleçler olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="63fd8-131">Bu işleçler, belirli bir konuma elektriler ekler veya yok eder.</span><span class="sxs-lookup"><span data-stu-id="63fd8-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="63fd8-132">Bunlar sırasıyla $a ^ \abger_j $ ve $a _j $ olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="63fd8-133">Örneğin, \begin{hizalaması} a ^ \abger_1 \ demet{0}_1 = \demet{1}_1, \dörtlü a ^ \hanger_1 \ ayraç{1}_1 = 0, \dörtlü A_1 \demet{0}_1 = 0, \dörtlü A_1 \tus{1}_1 = \tus{0}_1.</span><span class="sxs-lookup"><span data-stu-id="63fd8-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="63fd8-134">\end{hizalaması} buraya, ^ \abger_1 \ demet{1}_1 = 0 $ ve $a _1 \ ayraç{0}_1 ${0}değerini $a.</span><span class="sxs-lookup"><span data-stu-id="63fd8-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="63fd8-135">Bu tür işleçler hermitian veya Unitary değildir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="63fd8-136"><xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> türünü kullanarak genel oluşturma ve annihilasyon işleçlerini temsil ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="63fd8-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="63fd8-137">Örneğin, tek bir oluşturma işleci, takip olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="63fd8-138">Bu tür işleçleri de kullanarak Express $ $ \ket{0} \tus{1} \ayraç{1} \ayraç{0} = a ^ \abger_1 a ^ \dagger_2 \tus{0}^ {\otimes 4} olabilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="63fd8-139">$ $ Bu işleç dizisi, yukarıda göz önünde bulundurulduğuna benzer bir kod kullanılarak C# Hamiltonian simülasyon kitaplığı içinde oluşturulur:</span><span class="sxs-lookup"><span data-stu-id="63fd8-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="63fd8-140">$K $ Fermions sistemi için ikinci olarak, oluşturma işlecinin eylemini elde eden $a ^ \leger_i $ $ $ a ^ \abger_i \ket{n_1, n_2, \lnoktalar, 0_i, \lnoktalar, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \lnoktalar, 1_i tarafından verildi. , \lnoktalar, n_k}, $ $ ve $ $ a ^ \abger_i \ket{n_1, n_2, \lnoktalar, 1_i, \lnoktalar, n_k} = 0, $ $ burada $S _I = \sum_{j < i} a ^ \abger_j a_j $, tek bir parçacık durumunda olan ve $j < i $ dizinine sahip olan Fermıons sayısını ölçer.</span><span class="sxs-lookup"><span data-stu-id="63fd8-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="63fd8-141">Üçüncü bir operatör de genellikle ikinci bir satışta temsilde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="63fd8-142">Bu işleç, sayı işleci olarak bilinir ve \begin{Equation} n_i = a ^ \leger_i a_i tarafından tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="63fd8-143">\end{Equation} Bu işleç, \ Begin{hizalaması} n_i \tus{0}_I & = 0 \ olmayan\\belirten, belirli bir döndürme orblik 'in meslekini sayar </span><span class="sxs-lookup"><span data-stu-id="63fd8-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\
<span data-ttu-id="63fd8-144">n_i \ket{1}_i & = \ayraç{1}_I.</span><span class="sxs-lookup"><span data-stu-id="63fd8-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="63fd8-145">\end{hizalaması} yukarıdaki `FermionTerm` örneklerle benzerdir, bu sayı işleci aşağıdaki gibi oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="63fd8-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have ommitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="63fd8-146">Fermıonic sistemlerinde oluşturma veya alma işleçleri kullanılırken bir alt tlek ortaya çıktı.</span><span class="sxs-lookup"><span data-stu-id="63fd8-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="63fd8-147">Geçerli hisse madık etiketlerin değişimi altında simetrik bir değer olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="63fd8-148">Bu, $ $ a ^ \dagger_2 a ^ \ortager_1 \ demet{0} =-a ^ \abger_1 bir ^ \dagger_2 \tus{0}anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="63fd8-149">$ $ Bu tür işleçler ' Anti-commute ' olarak ve genel olarak herhangi bir $i için, j $ Bu \begin{hizalaması} bir ^ \abger_i a ^ \abger_j =-(1-\delta_{i, j}) a ^ \abger_j a ^ \abger_i, \dörtlü a ^ \hanger_i a_j = \delta_{i, j}-a_j a ^ \abger_i.</span><span class="sxs-lookup"><span data-stu-id="63fd8-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="63fd8-150">\end{hizalaması} bu nedenle, aşağıdaki iki <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> örneği inetiçele olarak kabul edilir</span><span class="sxs-lookup"><span data-stu-id="63fd8-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="63fd8-151">Oluşturma işleçlerini her birinin anti-commute, ikinci bir ölçü kullanan bir gösterimi kullanmanın, Fermıons 'ın yalarca siklerinin üzerinde karşılaştıkları zorlukları obviate anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="63fd8-152">Bunun yerine, sınama oluşturma işleçleri tanımımızda yeniden ortaya çıktı.</span><span class="sxs-lookup"><span data-stu-id="63fd8-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="63fd8-153">Anti-commutation kurallarını kullanarak bazı `LadderSequence` örnekleri, bazı durumlarda eksi işaretine kadar olan fermıonic işleçleri dizisine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="63fd8-154">Örneğin, Hamiltonian $a _0 ^ \hanger A_1 ^ \hanger A_1 a_0 =-A_1 ^ \hanger a_0 ^ \hanger A_1 a_0 $ değerini düşünün.</span><span class="sxs-lookup"><span data-stu-id="63fd8-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="63fd8-155">Bu, her `FermionTerm`için kurallı bir sıralama tanımlamamıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="63fd8-156">Her `FermionTerm` otomatik olarak aşağıdaki gibi kurallı sırayla yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="63fd8-157">İkinci Quantitik Gümıonic Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="63fd8-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="63fd8-158">Büyük olasılıkla, [elektronik sistemler için](xref:microsoft.quantum.chemistry.concepts.quantummodels) ücretlerdeki Hamiltonian 'nin oluşturma ve Ayla ilgili işleçler açısından yazılabilmesini unsurprising.</span><span class="sxs-lookup"><span data-stu-id="63fd8-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="63fd8-159">Özellikle, $ \psı\_j $, temeli oluşturan döndürme orbitleri ise</span><span class="sxs-lookup"><span data-stu-id="63fd8-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="63fd8-160">\begin{Equation} \hat{H} = \sum\_{PQ} H\_{PQ} a ^ \gesger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs} a ^ \dağılım\_p a ^ \dağılım\_q a\_ra\_s + h\_{\textrm NUC}, \label{EQ: Totalhemi} \end{Equation}; burada $h\_{\textrm NUC} $, Nunet enerji</span><span class="sxs-lookup"><span data-stu-id="63fd8-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="63fd8-161">\begin{hizalaması} h\_{pq} & = \int\_{-\infty} ^ \inf\psı ^\*\_p (x\_1) \left (-\frac{\nabla ^ 2}{2} + V (x\_1) \ right) \psı\_q (x\_1) \mathrm{d} ^ 3x @no__ t_9_ 1, \end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="63fd8-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="63fd8-162">Burada $V (x) $, ortalama alan potansiyeli ve</span><span class="sxs-lookup"><span data-stu-id="63fd8-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="63fd8-163">\begin{hizalaması} h\_{pqrs} & = \int\_{-\infty} ^ \inf, \ int\_{-\infty} ^ \infty\psı\_p ^\*(x\_1) \psi\_q ^\*(x\_2) \left (\frac{1}{| x_1-x_2 |} \ sağ) \psi\_r (x\_2) \psı\_s (x\_1) \mathrm{d} ^ 3x\_1 \ mathrm {d} ^ 3x\_2. \ Label {EQ: integrals} \end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="63fd8-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="63fd8-164">\_{PQ} $ $h terimleri tek bir elektron integrallarca alınır çünkü bu koşulların hepsi yalnızca tek elektriler ve benzer şekilde $h\_{pqrs} $ iki elektron integrallardır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-164">The terms $h\_{pq}$ are refered to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="63fd8-165">Bu katsayıların değerlerini hesaplamak bir integral gerektirdiğinden integrallar olarak adlandırılırlar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="63fd8-166">Tek bir elektron terimi, bireysel elektriklerin Kinetic enerji ve nuclei 'nin elektrik alanları ile etkileşimlerini anlatmaktadır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="63fd8-167">Diğer yandan iki elektron integrallarca, elektriler arasındaki etkileşimler açıklanır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="63fd8-168">Bu koşulların ne anlama geldiğini, her birini oluşturan oluşturma ve dumaılasyon işleçlerinden nasıl eğilebileceği.</span><span class="sxs-lookup"><span data-stu-id="63fd8-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="63fd8-169">Örneğin, $h _ {PQ} a ^ \abger_p A_Q $, orbbir $p $ öğesini dönmesi için değiştirici orbbir $q $ 'tan elektron hoppıng işlemini açıklar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="63fd8-170">Benzer şekilde, $h _ {pqrs} a ^ \abger_p a ^ \gesger_q a_r a_s $ (DISTINCT $p, q, r, s $) terimi, döndürme ve $r $ ile $s $ ve $p $ ve $q $ ' de iki elektrikinin kullanımını açıklar.</span><span class="sxs-lookup"><span data-stu-id="63fd8-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="63fd8-171">$R = q $ ve $p = s $ then $h _ {prrp} a ^ \abger_p a ^ \ortager_r a_r a_p = h_ {prrp} n_p N_R $, iki elektriğe yakın enerji cezası sunar, ancak bir dinamik işlemi tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="63fd8-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="63fd8-172">Bu tür Hamiltonians, aslında istenen tüm `FermionTerm` örneklerinin bulunduğu bir liste olan `FermionHamiltonian` sınıfını kullanarak temsil edebilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="63fd8-173">Hamiltonians hermitian as Definition olduğundan, koşulların eşit olup olmadığını denetlerken hermitian simetri kullanan `HermitianFermionTerm` daha özelleştirilmiş tür kullanarak terimleri dizinliyoruz.</span><span class="sxs-lookup"><span data-stu-id="63fd8-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="63fd8-174">Birkaç tanım örnek oluşturmamıza izin verin.</span><span class="sxs-lookup"><span data-stu-id="63fd8-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="63fd8-175">Hamiltonian $ \hat{H} = a_0 ^ \hanger A_1 + A_1 ^ \hanger a_0 $ değerini düşünün.</span><span class="sxs-lookup"><span data-stu-id="63fd8-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="63fd8-176">Hamiltonian işleçleri hermitian işleçleri olan olguyu kullanarak bu oluşturmayı basitleştirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="63fd8-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="63fd8-177">`Add`kullanarak Hamiltonian 'e terim eklerken, `fermionTerm0` gibi tüm hermitian terimlerinin hermitian eşleniği ile eşleştirilmek üzere olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="63fd8-178">Bu nedenle, aşağıdaki kod parçacığı aynı Hamiltonian 'yi de temsil eder:</span><span class="sxs-lookup"><span data-stu-id="63fd8-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="63fd8-179">Anti-commutation kurallarını kullanarak Hamiltonian içindeki bazı `FermionTerm` örnekleri, bazen eksi işaretine kadar, her zaman aynı fermıonic işleçleri dizisine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="63fd8-180">Örneğin, yukarıda oluşturulan koşulların toplamı olan Hamiltonian $H = a_0 ^ \hanger A_1 ^ \ortager A_1 a_0-A_1 ^ \hanger a_0 ^ \hanger A_1 a_0 = 2a_0 ^ \dağılım A_1 ^ \dağılım A_1 a_0 $ değerini düşünün.</span><span class="sxs-lookup"><span data-stu-id="63fd8-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="63fd8-181">Her zaman, bunların eşdeğer şartlar gibi kullanıcılara açık olmaz ve bu nedenle ayrıca Hamiltonian 'e ayrı olarak eklenebilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="63fd8-182">Alternatif olarak, birisi Hamiltonian 'de zaten var olan terimleri değiştirmek isteyebilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="63fd8-183">Bu durumlarda, eşdeğer terimleri aşağıdaki gibi birleştirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="63fd8-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="63fd8-184">Denk terimlerin katsayılarını birleştirerek Hamiltonian içindeki toplam terim sayısını azalttık.</span><span class="sxs-lookup"><span data-stu-id="63fd8-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="63fd8-185">Daha sonra, bu, Hamiltonian benzetimi için gereken hisse kapıları sayısını azaltır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="63fd8-186">İç Gösterim</span><span class="sxs-lookup"><span data-stu-id="63fd8-186">Internal Representation</span></span>

<span data-ttu-id="63fd8-187">Tek ve iki boyutlu etkileşimleri olan bir Fermionic Hamiltonian, şu şekilde ikinci quantitik gösterimde temsil edilir</span><span class="sxs-lookup"><span data-stu-id="63fd8-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="63fd8-188">$ $ \begin{hizalaması} H = \ Sum\_{PQ} h\_{PQ} a ^ \gesger\_{p} a\_{q} + \frac{1}{2}\sum\_{pqrs} h\_{pqrs} a ^ \gesger\_{p} a ^ \dağılım\_{q} a @no__ t_10_ {r} a\_{s}.</span><span class="sxs-lookup"><span data-stu-id="63fd8-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="63fd8-189">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="63fd8-189">\end{align} $$</span></span>

<span data-ttu-id="63fd8-190">Bu gösterimde, en çok $N ^ 2 + N ^ 4 $ katsayılar vardır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="63fd8-191">Ancak, bu katsayıların birçoğu aynı işlece karşılık geldiği için toplanabilir.</span><span class="sxs-lookup"><span data-stu-id="63fd8-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="63fd8-192">Örneğin, $p, s $, r, s $ ' nin farklı dizinler olduğu durumlarda, commutation '\_a bir ^ \dağılım\_{q} a\_{r} a\_{s} =-a ^ \dağılım\_{q} a ^ \gesger\_{ p} a\_{r} a\_{s} =-a ^ \dağılım\_{p} a ^ \dağılım\_{q} a\_{s} a\_{r} = a ^ \dağılım\_{s} a\_{r}.</span><span class="sxs-lookup"><span data-stu-id="63fd8-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="63fd8-193">Ayrıca, $H $ olduğu gibi, hermitian fermıonic işlecinin her birinde $h\_{pqrs} bir ^ \dağılım\_{p} bir ^ \dağılım\_{q}\_{r}\_{s} $, $H $ içinde de bulunan bir hermitian eşleniği vardır.</span><span class="sxs-lookup"><span data-stu-id="63fd8-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="63fd8-194">Bu symmetries sahip olan terim gruplarını benzersiz bir şekilde indekslemek için, dizinler $ (i\_1, \cnoktalar, ı\_n, j\_1, \cnoktalar, j\_m) $ ' nin herhangi bir dizisinin $n + m $ fermıonic işleçlerini $a ^ \dağılım\_{ı\_1} \cnoktalara bir ^ \dağılım\_{i\_n} a\_{j\_1} \cnoktalar a\_{j\_m} $as aşağıdaki:</span><span class="sxs-lookup"><span data-stu-id="63fd8-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="63fd8-195">^ \Dağılım\_{i\_\cdot} $ $a tüm oluşturma işleçleri, tüm annıılasyon işleçleri $a\_{j\_\cdot} $ öğesinden önce yerleştirildi.</span><span class="sxs-lookup"><span data-stu-id="63fd8-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="63fd8-196">Tüm oluşturma işleci dizinleri artan düzende sıralanır; bu $i\_1 < ı\_2 < \cnoktalar < ı\_n $.</span><span class="sxs-lookup"><span data-stu-id="63fd8-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="63fd8-197">Tüm Ayla ilgili işleç dizinleri azalan düzende sıralanır; bu $j\_1 > j\_2 \ cnoktalar > j\_d $ olur.</span><span class="sxs-lookup"><span data-stu-id="63fd8-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="63fd8-198">En soldaki Dizin, en sağdaki dizinden daha küçüktür veya eşittir, bu $i\_1 \ Le j\_d $.</span><span class="sxs-lookup"><span data-stu-id="63fd8-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="63fd8-199">Bu kurallı sıralı dizin kümesini $ $ \begin{hizalaması} (i\_1, \cnoktalar, ı\_n, j\_1, \cnoktalar, j\_m) \ '\_{n, m} olarak tanımmıza izin verin.</span><span class="sxs-lookup"><span data-stu-id="63fd8-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="63fd8-200">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="63fd8-200">\end{align} $$</span></span>

<span data-ttu-id="63fd8-201">Bu kurallı sıralama ile fermıonic Hamiltonian, $ $ \begin{hizalaması} H = \sum\_{(p, q) \ in S\_{1,1}} H '\_{PQ} \frac{a ^ \hanger\_{p} bir\_{q} + bir ^ \ dağılım\_{q} a\_{ p}}{2}+ \ Sum\_{(p, q, r, s) \ in S\_{2,2}} h '\_{pqrs} \frac{a ^ \hanger\_{p} bir ^ \dağılım\_{q} a\_{s} a ^ \ dağılım\_{r} bir\_{q} a\_{p}}{2}, \end{hizalaması} $ $, tek ve iki elektron integrals $h '\_{PQ} $ ve $h '\_{pqrs} $, sırasıyla.</span><span class="sxs-lookup"><span data-stu-id="63fd8-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

