---
title: Hartree-Fock teorisi | Microsoft Docs
description: Hartree-Fock teorik belgeleri
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: e73111ae710e11ca6730581b8be711cf32783677
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184109"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="92c7c-103">Hartree – Fock teorisi</span><span class="sxs-lookup"><span data-stu-id="92c7c-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="92c7c-104">Hisse kutları benzetiminde en önemli miktar, Hamiltonian matrisin en düşük enerji eigenvector değeri olan zemin durumudur.</span><span class="sxs-lookup"><span data-stu-id="92c7c-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="92c7c-105">Bunun nedeni, yeniden eylem oranları gibi oda sıcaklık miktarlarındaki en fazla motacules 'in, bir yeniden eylem yasındaki adımın başlangıcını ve sonunu betimleyen hisse ve ara sıcaklık durum genellikle taban durumlardır.</span><span class="sxs-lookup"><span data-stu-id="92c7c-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="92c7c-106">Baş durum, genellikle daha fazla bilgi almak için çok zor olsa da (hisse bir bilgisayar ile bile), katlanarak çok sayıda yapılandırma üzerinden bir dağıtım olduğundan.</span><span class="sxs-lookup"><span data-stu-id="92c7c-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="92c7c-107">Zemin eyalet enerji gibi miktarlar öğrenilebilir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="92c7c-108">Örneğin, $ \ket{\psı} $ herhangi bir saf hisse durumundaysa, \begin{Equation} E = \bra{\psı} \hat{H} \ket{\psı} \end{Equation}, sistemin o durumda sahip olduğu ortalama enerji sağlar.</span><span class="sxs-lookup"><span data-stu-id="92c7c-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="92c7c-109">Bu durumda, bu değer en küçük değeri veren durumdur.</span><span class="sxs-lookup"><span data-stu-id="92c7c-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="92c7c-110">Sonuç olarak, doğru zemin durumu için mümkün olduğunca yakın olan bir durumun seçilmesi, doğrudan enerjiyi tahmin etmek için (değişen bir sanal bölge kapsamında olduğu gibi) ya da aşama tahmini aracılığıyla önemli bir durum seçmektir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="92c7c-111">Hartree – Fock teorik, hisse sistemleri için ilk durumu oluşturmak için basit bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="92c7c-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="92c7c-112">Bir hisse sisteminin zemin durumu için tek bir sdaha daha sonra determinantı verir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="92c7c-113">Bu uçta, boşluk enerji alanını en aza indiren, Fock-Space içinde bir döndürme bulur.</span><span class="sxs-lookup"><span data-stu-id="92c7c-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="92c7c-114">Özellikle, $N $ Elektriklerde bir sistem için yöntem, döndürme \begin{Equation} \prod_{j = 0} ^ {N-1} a ^ \abger_j \tus{0} \mapsto \prod_{j = 0} ^ gerçekleştirir {N-1} e ^ {u} a ^ \abger_j e ^ {-u} \tus{0}\defeq\prod_{j = 0} ^ {N-1} \widetilde{a} ^ \kama ger _j \ket{0}, \end{Equation} bir anti-hermitian (yani $u =-u ^ \linger $) matrisi $u = \sum_{PQ} u_ {PQ} a ^ \linger_p A_Q $.</span><span class="sxs-lookup"><span data-stu-id="92c7c-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="92c7c-115">$U $ matrisinin orbilaçlerini ve $ \widetilde{a} ^ \linger_j $ ve $ \widetilde{a}_j $ ' i temsil ettiğinden, elektriksel molesel döndürme-Orbitals için oluşturma ve annimilasyon işleçlerini temsil etmelidir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="92c7c-116">$U $ matrisi, daha sonra beklenen enerji $ \bra{0} \prod_{j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \dagger_k\ket{0}$ değerini en iyi duruma getirdi.</span><span class="sxs-lookup"><span data-stu-id="92c7c-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="92c7c-117">Bu iyileştirme sorunları genel olarak oldukça zor olabilir; böylece, Hartree – Fock algoritması en iyi duruma getirme sorununa hızlı bir şekilde yakınsama eğilimi yaparak, özellikle de eşitlenmiş-Shell molecuları için daha yakın bir çözüm sağlar.</span><span class="sxs-lookup"><span data-stu-id="92c7c-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="92c7c-118">Bu durumları `FermionWavefunction` nesnesinin bir örneği olarak belirteceğiz.</span><span class="sxs-lookup"><span data-stu-id="92c7c-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="92c7c-119">Örneğin, $a ^ \abger_{1}a ^ \abger_{2}bir ^ \abger_{6}\demet{0}$, aşağıdaki gibi kimya kitaplığında örneği oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="92c7c-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="92c7c-120">Ayrıca, `SpinOrbital` dizinlerle dalga işlevlerinin dizinini oluşturup bu dizinleri aşağıdaki gibi tamsayılara dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="92c7c-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="92c7c-121">Hartree – Fock teorik özelliği ile ilgili en çarpıcı özellik, Elektriklerde hiçbir entanglement 'e sahip olmayan bir hisse</span><span class="sxs-lookup"><span data-stu-id="92c7c-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="92c7c-122">Bu, genellikle, molesel sistemlerin özelliklerinin uygun bir niteleyici açıklaması sağladığı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="92c7c-123">Hartree-Fock durumu ayrıca bir `FermionHamiltonian` aşağıdaki şekilde yeniden oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="92c7c-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="92c7c-124">Bununla birlikte, özellikle de kesin bağıntılı sistemler için doğru sonuçlar elde etmek, Hartatin teorik, çok fazla</span><span class="sxs-lookup"><span data-stu-id="92c7c-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>