---
title: Bağıntılı dalga fonksiyonları
description: Microsoft hisse Kimya kitaplığı 'nı kullanarak dalga işlevlerinde dinamik ve dinamik olmayan bağıntılar hakkında bilgi edinin.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: ab3d90d79c7c14a1ef5b3aa833df49be186f3dd7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856267"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="5b3b4-103">Bağıntılı dalga fonksiyonları</span><span class="sxs-lookup"><span data-stu-id="5b3b4-103">Correlated wavefunctions</span></span>

<span data-ttu-id="5b3b4-104">Birçok sistem için, özellikle de equlebrium geometrisi, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teorisi, tek bir determinkasel başvuru durumu aracılığıyla molesel Özellikler 'in bir nitel açıklaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="5b3b4-105">Ancak, nicel doğruluğunu sağlamak için bir diğeri de bağıntı efektlerini dikkate almalıdır.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="5b3b4-106">Bu bağlamda, dinamik ve dinamik olmayan eş ilişkiler arasında dinstinguma etmek önemlidir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="5b3b4-107">Dynamical bağıntılar, elektrik 'ın, ınterelectronic itme gibi nedenlerle sürekli kalmalarına neden olularak oluşur.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="5b3b4-108">Bu efekt, başvuru durumundaki elektriler 'in exalıntılar 'i göz önünde bulundurarak modellenebilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="5b3b4-109">Wavefunction, sistemin yalnızca bir niteleyici açıklamasına ulaşmak için bile, dalga işlevi iki veya daha fazla yapılandırma tarafından daha düzgün sırada olduğunda ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="5b3b4-110">Bu, belirleyici bir üst konuma sahiptir ve multireference wavefunction örneğine bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="5b3b4-111">Kimya kitaplığı, çok başvurulu bir sıra wavefunction 'ı belirleyici bir üst konum olarak belirtmek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="5b3b4-112">Seyrek multireference dalga işlevlerini çağırdığımız bu yaklaşım, yalnızca birkaç bileşen üst konumu belirlemek için yeterli olduğunda etkilidir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="5b3b4-113">Kitaplık Ayrıca, genelleştirilmiş Unitary ile bağlanmış küme ANSATZ aracılığıyla tek bir temelinde başvurunun üzerine dinamik bağıntılar dahil etmek için bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="5b3b4-114">Ayrıca, bu durumlar için bir hisse bilgisayarında bu durumları oluşturan hisse devreleri de oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="5b3b4-115">Bu durumlar [broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)belirlenebilir ve ayrıca bu durumları Kimya kitaplığı aracılığıyla el ile belirtme işlevlerini de sağlarız.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="5b3b4-116">Seyrek Multi-Reference wavefunction</span><span class="sxs-lookup"><span data-stu-id="5b3b4-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="5b3b4-117">Çok başvurulu bir durum $ \ket{\ psi_ {\rm {MCSCF}}} $ açıkça $N $-elektron sdaha belirleyici bir şekilde doğrusal bir bileşim olarak belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="5b3b4-118">\begin{hizalaması} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cnoktalar < i_N} \ lambda_ {i_1, i_2, \cnoktalar, i_N} a ^ \ dagger_ {İ_1} a ^ \ dagger_ {i_2} \tıı {0} .</span><span class="sxs-lookup"><span data-stu-id="5b3b4-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="5b3b4-119">\end{hizalaması} Örneğin, $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) {0} \tus$, aşağıdaki gibi kimya kitaplığında belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="5b3b4-120">Üst konum bileşenlerinin bu açık gösterimi yalnızca birkaç bileşenin belirtilmesi gerektiğinde etkilidir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="5b3b4-121">İstenen durumu doğru bir şekilde yakalamak için birçok bileşen gerektiğinde bu gösterimi kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="5b3b4-122">Bunun nedeni, bu durumu bir hisse bilgisayar üzerinde hazırlayan, en az üst konum bileşenleri ile en az doğrusal bir şekilde ölçeklendirilen ve üst konum güçlerinin tek bir norm ile en fazla çeyrek bir şekilde ölçeklendirilebilen, hisse başında bu durumu sağlayan geçit 'in bulunduğu kapı maliyetidir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="5b3b4-123">Unitary ile bağlanmış küme wavefunction</span><span class="sxs-lookup"><span data-stu-id="5b3b4-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="5b3b4-124">Ayrıca, bir Unitary ile bağlanmış küme wavefunction $ \ket{\ psi_ {\rm {UCC}}} $, chemistery kitaplığını kullanarak belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="5b3b4-125">Bu durumda, tek bir determinantik başvuru durumuna sahip olduğumuz $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="5b3b4-126">Unitary ile bağlanmış küme dalga işlevinin bileşenleri, bir başvuru durumunda işlem gören Unitary operatörü aracılığıyla implicity belirtilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="5b3b4-127">Bu Unitary işleci genellikle $e ^ {T-T ^ \abger} $ olarak yazılmıştır; burada $T-T ^ \dağılım $, Anti-hermitian küme operatöründür.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="5b3b4-128">Bu nedenle \begin{hizalaması} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\Rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="5b3b4-129">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="5b3b4-129">\end{align}</span></span>

<span data-ttu-id="5b3b4-130">Ayrıca, $T = T_1 + T_2 + \cnoktalar $ Cluster işlecinin parçalara bölünmesi, her parça $T _j $ gövde terimlerini $j.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="5b3b4-131">Genelleştirilmiş bağlanmış küme teorik 'inde, tek gövde küme operatörü (Singles), \begin{hizalaması} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{hizalaması} biçiminde</span><span class="sxs-lookup"><span data-stu-id="5b3b4-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="5b3b4-132">ve iki gövdede küme işleci (Double 'lar), \begin{hizalaması} T_2 = \ sum_ {pqrs} T ^ {PQ} _ {RS}. dagger_p bir ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="5b3b4-133">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="5b3b4-133">\end{align}</span></span>

<span data-ttu-id="5b3b4-134">Daha yüksek sıralı terimler (üçlü ve çeyrek Rupisi, vb.) mümkündür, ancak şu anda Kimya kitaplığı tarafından desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="5b3b4-135">Örneğin, $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 {0} \tus$ ve dagger_0 $T = 0,123 a ^ \ A_1 dagger_0a + 0,456 0,789 a ^ \ dagger_3 ^ \ A_1 a_2 dagger_3a $.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="5b3b4-136">Bu durum, aşağıdaki gibi kimya kitaplığı 'nda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="5b3b4-137">Dönüş dönüştürmesi, `SpinOrbital` tamsayı dizinleri yerine dizinler belirtilerek açıkça yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="5b3b4-138">Örneğin psi_, < \ dagger_ {1, \upoklu} a ^ \ dagger_ {2, \downarrow}\ket {0} $ ve let $T = 0,123 a ^ \ dagger_ {0, \upoklu} a_ {1, \upoklu} + 0,456 a ^ \ dagger_ {0, \upoklu} a ^ \ dagger_ {3, \downok} a_ {1, \upoklu} a_ {2, \downconvserving}-0,789 a ^ \ dagger_ {3, \upoklu} dagger_ {1, \upoklu} a_,.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="5b3b4-139">Bu durum, aşağıdaki gibi kimya kitaplığı 'nda oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="5b3b4-140">Ayrıca, Gamze 'nin yalnızca dönüş-yörünbitleri ve yalnızca dolu döndürme-orbitleri ile birlikte kapladığı küme işleçlerini numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="5b3b4-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
