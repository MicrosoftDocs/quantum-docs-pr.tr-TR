---
title: Hamiltonian Dynamics benzetimi
description: Hamiltonian benzetimleriyle çalışmak için Trour-Suzuki formüllerini ve qubitişmeyi nasıl kullanacağınızı öğrenin.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 5dad4e4a77eea99e72eb2efac52eec61ebbdb21c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275933"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="b5e41-103">Hamiltonian Dynamics benzetimi</span><span class="sxs-lookup"><span data-stu-id="b5e41-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="b5e41-104">Hamiltonian, temel alınan işleçlerin toplamı olarak belirtiledikten sonra, daha sonra iyi bilinen tekniklerin bir konak kullanılarak temel geçit işlemlerine derlenebilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="b5e41-105">Üç verimli yaklaşımlar şunlardır: Suzuki formülleri, birimlere ait doğrusal birleşimler ve qutoleştirme.</span><span class="sxs-lookup"><span data-stu-id="b5e41-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="b5e41-106">Aşağıdaki üç yaklaşımı anladık ve Hamiltonian simülasyon kitaplığını kullanarak bu yöntemlerin nasıl uygulanacağını gösteren somut Q # örnekleri verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="b5e41-107">Trour – Suzuki formülleri</span><span class="sxs-lookup"><span data-stu-id="b5e41-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="b5e41-108">Trour – Suzuki formüllerinin arkasındaki fikir basittir: Hamiltonian 'ın, Hamiltonians benzetimi yapma ve sonra toplam evrimini bu daha basit Evolutions bir sıra olarak yaklaşık olarak ifade edin.</span><span class="sxs-lookup"><span data-stu-id="b5e41-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="b5e41-109">Özellikle de $H = \ sum_ {j = 1} ^ m H_j $ Hamiltonian olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="b5e41-110">Ardından, $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, bu değer $t \ll $1 olduğunda, bu yaklaşık olarak oluşan hata gözardı edilebilir hale gelir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="b5e41-111">$E ^ {-i H t} $ sıradan bir üstel ise, bu her bir hatanın $O (m ^ 2 t ^ 2) $: sıfır olacağını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b5e41-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="b5e41-112">Bu hata oluşur $e çünkü ^ {-iHt} $, bir işleç üstel ve bunun sonucu olarak, $H _j $ koşullarının çalışmamasından dolayı bu formül kullanılırken bir hata oluştu (*Örneğin*, $H _j H_k H_k, genel olarak).</span><span class="sxs-lookup"><span data-stu-id="b5e41-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="b5e41-113">$T $ büyükse, Trour – Suzuki formülleri, bir kısa saat adımları dizisine ayırarak Dynamics 'in doğru benzetimini yapmak için yine de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="b5e41-114">$R $ ' ın evrimde geçen adım sayısı olmasına izin verin. bu nedenle, her adım $t/r $ için her seferinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-114">Let $r$ be the number of steps taken in the time evolution, so each time step runs for time $t/r$.</span></span> <span data-ttu-id="b5e41-115">Daha sonra $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r), $ $ $r $, $m ^ 2 t ^ 2/\ Epsilon $ olarak ölçeklendirirken, bu hatanın herhangi bir $ \epsilon>$0 için en fazla $ \epsilon $ üzerinden yapılabilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="b5e41-116">Hata koşullarının iptal edildiğini belirten bir işleç üs sırası oluşturarak daha doğru yaklaşık bir daha yakın şekilde oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="b5e41-117">En basit bu formül, ikinci sıra Trour-Suzuki formülü, $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} biçimini alır ^ 1 e ^ {-iH_j t/2R} \ right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $ olarak ölçeklendirmek için $r $ ' i seçerek herhangi bir $ \epsilon>$0 ' den daha az bir hata olabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-117">The simplest such formula, the second order Trotter-Suzuki formula, takes the form $$ U_2(t) = \left(\prod_{j=1}^{m} e^{-iH_j t/2r} \prod_{j=m}^1 e^{-iH_j t/2r}\right)^r = e^{-iHt} + O(m^3 t^3/r^2), $$ the error of which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="b5e41-118">Daha yüksek sıralı formüller, özellikle de ($ 2k $) $k>$0 için tek sıra, yinelemeli olarak oluşturulabilir: $ $ U_ {2k} (t) = [U_ {2k-2} (s_k \~ t)] ^ 2 u_ {2k-2} ([1-4s_k] t) [u_ {2k-2} (s_k \~ t)] ^ 2 = e ^ {-iht} + O ((m t) ^ {2k + 1}/r ^ {2k}), $ $ burada $s _K = (4-4 ^ {1/(2k-1)}) ^ {-1} $.</span><span class="sxs-lookup"><span data-stu-id="b5e41-118">Even higher-order formulas, specifically ($2k$)th-order for $k>0$, can be constructed recursively: $$ U_{2k}(t) = [U_{2k-2}(s_k\~ t)]^2 U_{2k-2}([1-4s_k]t) [U_{2k-2}(s_k\~ t)]^2 = e^{-iHt} + O((m t)^{2k+1}/r^{2k}), $$ where $s_k = (4-4^{1/(2k-1)})^{-1}$.</span></span>

<span data-ttu-id="b5e41-119">En basit, Suzuki tarafından ilk olarak tanıtılan aşağıdaki dördüncü sıra ($k = $2) formüldür: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-IHV t} + O (m ^ 5T ^ 5/r ^ 4), $ $ burada $s _2 = (4-4 ^ {1/3}) ^ {-1} $.</span><span class="sxs-lookup"><span data-stu-id="b5e41-119">The simplest is the following fourth order ($k=2$) formula, originally introduced by Suzuki: $$ U_4(t) = [U_2(s_2\~ t)]^2 U_2([1-4s_2]t) [U_2(s_2\~ t)]^2 = e^{-iHt} +O(m^5t^5/r^4), $$ where $s_2 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="b5e41-120">Genel olarak, yoğun yüksek sıralı formüller benzer şekilde oluşturulabilir; Bununla birlikte, daha karmaşık tümleştiricileri kullanmanın maliyeti genellikle pek çok pratik sorun için dördüncü sıra avantajlarının dışındadır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="b5e41-121">Yukarıdaki stratejilerin çalışmasını sağlamak için, $e ^ {-iH_j t} $ geniş bir sınıfının benzetimini yapmak için bir yönteme ihtiyacımız var.</span><span class="sxs-lookup"><span data-stu-id="b5e41-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="b5e41-122">En basit Hamiltonians ailesi ve en çok faydalı olan, burada kullanabiliriz Pauli işleçleri.</span><span class="sxs-lookup"><span data-stu-id="b5e41-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="b5e41-123">Pauli işleçleri, Clienfford işlemleri (hisse bilgi işlem ortamında standart kapıları) kullanılarak diagonalized olabileceğinden kolayca benzetilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="b5e41-124">Ayrıca, diagonalized olduktan sonra eigenvalues, üzerinde davranabilecekleri qubits 'in eşliği hesaplanırken bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="b5e41-125">Örneğin, $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ burada $ $ e ^ {-ı Z \otimes Z t} = \begin{bmatrix} e ^ {-it} & 0 & 0 & 0</span><span class="sxs-lookup"><span data-stu-id="b5e41-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="b5e41-126">0 & e ^ {i t} & 0 & 0</span><span class="sxs-lookup"><span data-stu-id="b5e41-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="b5e41-127">0 & 0 & e ^ {it} & 0</span><span class="sxs-lookup"><span data-stu-id="b5e41-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="b5e41-128">0 & 0 & 0 & e ^ {-it} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="b5e41-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="b5e41-129">$ $ Burada, $e ^ {-iHt} {00} \tus= e ^ {it} {00} \tus$ ve $e ^ {-iht} {01} \tus= e ^ {-it} {01} \tus$, "$0 $, 1. bit $1 dizesinin eşliği $1 $ iken $0 $,</span><span class="sxs-lookup"><span data-stu-id="b5e41-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="b5e41-130">Pauli işleçlerinin üsleri, işlem kullanılarak doğrudan Q # içinde uygulanabilir <xref:microsoft.quantum.intrinsic.exp> :</span><span class="sxs-lookup"><span data-stu-id="b5e41-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="b5e41-131">Fermıonic Hamiltonians için, [Ürdün – Wigner ayrıştırma](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , Hamiltonian 'Yi Pauli işleçleri toplamı ile eşleştirir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="b5e41-132">Bu, yukarıdaki yaklaşımın Chemistry benzetimi için kolayca uyarlanabilme anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="b5e41-133">Aşağıda, Ürdün-Wigner temsilindeki tüm Pauli terimleri üzerinde el ile döngü yapmak yerine, aşağıdaki gibi bir simülasyonu nasıl yürütüp bakacağından basit bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="b5e41-134">Başlangıç noktanızda, sınıfın bir örneği olarak kodda ifade edilen Fermıonic Hamiltonian 'in bir [Ürdün-Wigner kodlaması](xref:microsoft.quantum.chemistry.concepts.jordanwigner) vardır `JordanWignerEncoding` .</span><span class="sxs-lookup"><span data-stu-id="b5e41-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="b5e41-135">Bu, Q # benzetim algoritmaları tarafından tüketilebilir olan Ürdün-Wigner gösteriminin bu biçimi Kullanıcı tanımlı bir türdür `JordanWignerEncodingData` .</span><span class="sxs-lookup"><span data-stu-id="b5e41-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="b5e41-136">Q # içinde, bu biçim, `TrotterStepOracle` yürütülmesi için gereken diğer parametrelere ek olarak, bir işleci (Suzuki tümleştirici) kullanarak zaman evrimini yaklaştıran bir operatör döndüren kolay bir işleve geçirilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="b5e41-137">Bu uygulamada, bu uygulama, [hisse bilgisayarları kullanarak elektronik yapı Hamiltonians simülasyonuna](https://arxiv.org/abs/1001.3855) [ilişkin](https://arxiv.org/abs/1403.1539) bazı iyileştirmeler uygular ve bu, gereken tek qubit döndürme sayısını en aza indirmek ve simülasyon hatalarını azaltmayı sağlar.</span><span class="sxs-lookup"><span data-stu-id="b5e41-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="b5e41-138">Qubitişleştirme</span><span class="sxs-lookup"><span data-stu-id="b5e41-138">Qubitization</span></span>

<span data-ttu-id="b5e41-139">Qubitişleştirme, hisse ve hisse için hisse</span><span class="sxs-lookup"><span data-stu-id="b5e41-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="b5e41-140">Qubitişleştirme, bir defadan fazla qubits gerektirdiğinden, yöntem, evlenme süresi ve hata toleransı ile en uygun ölçeklendirmeyi kabul eder.</span><span class="sxs-lookup"><span data-stu-id="b5e41-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="b5e41-141">Bu nedenlerden dolayı, genel olarak Hamiltonian Dynamics 'in benzetimini yapmak ve özel olarak elektronik yapı sorununu çözmek için sık kırmızı bir yöntem haline gelmiştir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="b5e41-142">Yüksek bir düzeyde, bu, aşağıdaki adımlarla bu işlemleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="b5e41-143">İlk olarak, $H = \ sum_j h_j H_j $ Unitary ve hermitian $H _j $ ve $h _j \ge $0.</span><span class="sxs-lookup"><span data-stu-id="b5e41-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="b5e41-144">Bir dizi yansıma gerçekleştirmeyle, qubitişleştirme $ $W = e ^ {\pm i \cos ^ {-1} (H/| h | _1)}, $ $ $ $ $ | h | _1 = \ sum_j | h_j | $ ile eşdeğer bir işleç uygular.</span><span class="sxs-lookup"><span data-stu-id="b5e41-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="b5e41-145">Sonraki adımda, $e ^ {i\pm \ Cos ^ {-1} (E_k/| h | _1)} $, $E _K $ değerinin $H $ ' in eigenvalues değeri ^ {-$e t} $ değerine dönüştürülmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="b5e41-146">Bu, [hisse sinyali işleme](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501)dahil olmak üzere çeşitli hisse ve değer dönüştürme yöntemleri kullanılarak elde edilebilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="b5e41-147">Alternatif olarak, yalnızca statik miktarlar isteniyorsa (Hamiltonian 'nin zemin durumu enerjisi gibi), sonucun kosinüsünü alarak sonuçtan zemin durumu enerji tahminini tahmin etmek için doğrudan $W $ ' a kadar [aşama tahmini](xref:microsoft.quantum.libraries.characterization) uygulamayı da yeterli olacaktır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="b5e41-148">Bu durum, Spectral dönüştürmesinin, bir hisse değeri dönüştürme yöntemi kullanmak yerine sınıf aracılığıyla gerçekleştirilmesini sağladığından önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="b5e41-149">Daha ayrıntılı bir düzeyde, qubitişleştirme uygulanması Hamiltonian için arabirimler sağlayan iki alt yordam gerektirir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="b5e41-150">Trour – Suzuki metotlarından farklı olarak, bu alt yordamlar ücretlendirilir ve uygulamaları, bir mahkeme dayalı simülasyonu için gerekli olacak şekilde, logaritmayı çok daha fazla qubit kullanmayı gerektirmeyecektir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="b5e41-151">Karşılık gelen ilk hisse alt yordam $ \operatorname{Select} $ olarak adlandırılır ve her bir $H _j $ ' nin hermitian ve Unitary olarak kabul edildiği \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psı}, \end{Equation} olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="b5e41-152">Bu durum kısıtlayıcı gibi görünse de Pauli işleçlerinin hermitian ve Unitary olduğunu ve bu nedenle hisse kamistry simülasyonu gibi uygulamaların bu çerçeveye doğal olarak düştüğünü hatırlayın.</span><span class="sxs-lookup"><span data-stu-id="b5e41-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="b5e41-153">Büyük olasılıkla tahmin edilecek $ \operatorname{Select} $ işlemi, aslında bir yansıma işlemidir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="b5e41-154">Bu, her bir $H _j $ Unitary ve hermitian olduğundan ve dolayısıyla ıdgenvalues $ \pm $1 ' i içerdiğinden, $ \operatorname{Select} ^ 2 \ demet {j} \ket{\psı} = \ket{j} \ket{\psi} $ 'ın bu şekilde görülebilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="b5e41-155">İkinci altyordam $ \operatorname{Prepare} $ olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="b5e41-156">Select işlemi, her Hamiltonian terimlerinin her biri için tutarlı bir yol sağlarken $H _j $ Prepare alt yordamı $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}'e erişmek için bir yöntem sunar.</span><span class="sxs-lookup"><span data-stu-id="b5e41-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="b5e41-157">\end{Equation} ardından, çarpma kontrollü bir aşama kapısı kullanarak $ $ \Lambdad\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \Text{If} x = 0 olduğunu görüyoruz</span><span class="sxs-lookup"><span data-stu-id="b5e41-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="b5e41-158">\ket{x} & \Text{otherwise} \end{Cases}.</span><span class="sxs-lookup"><span data-stu-id="b5e41-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="b5e41-159">$ \Operatorname{Prepare} $ işlemi doğrudan qubitişleştirme içinde kullanılmaz, ancak bunun yerine $ \operatorname{Prepare} $ 'ın $ $ \begin{hizalaması} R &amp; = 1-2 \ operatorname {Prepare} {0} \tus\bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \lambda \operatorname{Prepare} ^ {-1} oluşturduğunu belirten bir yansıma uygulamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="b5e41-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="b5e41-160">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="b5e41-160">\end{align} $$</span></span>

<span data-ttu-id="b5e41-161">$W $, yürüme işleci, $ \operatorname{Select} $ ve $R $ işlemleri $ $ W = \operatorname{Select} R olarak ifade edilebilir. Bu, "^ {\pm i \cos ^ {-1} (H/| H | _1)} $ $e için eşdeğer bir işleç (bir ıometry 'ye kadar) uygulamak için yeniden görünebilen $ $.</span><span class="sxs-lookup"><span data-stu-id="b5e41-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="b5e41-162">Bu alt yordamlar, Q # ' da kolayca ayarlanabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="b5e41-163">Örnek olarak, $H = X_1 + X_2 + Z_1 Z_2 $ ' nin bulunduğu basit qubit çapraz-şaşırtıcı Hamiltonian 'yi düşünün.</span><span class="sxs-lookup"><span data-stu-id="b5e41-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="b5e41-164">Bu durumda, $ \operatorname{Select} $ işlemini uygulayacak olan Q # kodu tarafından çağrılır <xref:microsoft.quantum.canon.multiplexoperations> ; ancak, $ \operatorname{Prepare} $ işlemi kullanılarak uygulanabilir <xref:microsoft.quantum.preparation.preparearbitrarystate> .</span><span class="sxs-lookup"><span data-stu-id="b5e41-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="b5e41-165">Hubbard modelinin benzetimini yapmayı içeren bir örnek, bir [Q # örneği](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)olarak bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="b5e41-166">Rastgele Kimya sorunları için bu adımları el ile belirtmek çok çaba gerektirir, bu da Kimya kitaplığı kullanmaktan kaçınılmaz.</span><span class="sxs-lookup"><span data-stu-id="b5e41-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="b5e41-167">Yukarıdaki Trour – Suzuki simülasyon algoritmasına benzer şekilde,, `JordanWignerEncodingData` `QubitizationOracle` yürütülmesi için gereken diğer parametrelere ek olarak, yürüme işlecini döndüren kolaylık işlevine geçirilir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="b5e41-168">Daha da önemlisi, uygulama <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> Pauli dizelerinin doğrusal bir birleşimi olarak belirtilen rastgele Hamiltonians için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b5e41-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="b5e41-169">Kimya benzetimleri için en iyi duruma getirilmiş bir sürüm kullanılarak çağrılır <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> .</span><span class="sxs-lookup"><span data-stu-id="b5e41-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="b5e41-170">Bu sürüm, [Doğrusal t karmaşıklığıyla, elektronik Spectra 'in, doğrusal bir şekilde kodlama](https://arxiv.org/abs/1805.03662)bölümünde ele alınan teknikleri kullanarak T geçitleri sayısını en iyi duruma getirdi.</span><span class="sxs-lookup"><span data-stu-id="b5e41-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>