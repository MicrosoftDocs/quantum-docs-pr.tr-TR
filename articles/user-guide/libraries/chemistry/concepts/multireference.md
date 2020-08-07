---
title: Bağıntılı dalga fonksiyonları
description: Microsoft hisse Kimya kitaplığı 'nı kullanarak dalga işlevlerinde dinamik ve dinamik olmayan bağıntılar hakkında bilgi edinin.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0066d676205901d4f2d41538684f9ba57407eb82
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869571"
---
# <a name="correlated-wavefunctions"></a>Bağıntılı dalga fonksiyonları

Birçok sistem için, özellikle de equlebrium geometrisi, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teorisi, tek bir determinkasel başvuru durumu aracılığıyla molesel Özellikler 'in bir nitel açıklaması sağlar. Ancak, nicel doğruluğunu sağlamak için bir diğeri de bağıntı efektlerini dikkate almalıdır. 

Bu bağlamda, dinamik ve dinamik olmayan eş ilişkiler arasında dinstinguma etmek önemlidir.
Dynamical bağıntılar, elektrik 'ın, ınterelectronic itme gibi nedenlerle sürekli kalmalarına neden olularak oluşur. Bu efekt, başvuru durumundaki elektriler 'in exalıntılar 'i göz önünde bulundurarak modellenebilir. Wavefunction, sistemin yalnızca bir niteleyici açıklamasına ulaşmak için bile, dalga işlevi iki veya daha fazla yapılandırma tarafından daha düzgün sırada olduğunda ortaya çıkar.
Bu, belirleyici bir üst konuma sahiptir ve multireference wavefunction örneğine bir örnektir.

Kimya kitaplığı, çok başvurulu bir sıra wavefunction 'ı belirleyici bir üst konum olarak belirtmek için bir yol sağlar. Seyrek multireference dalga işlevlerini çağırdığımız bu yaklaşım, yalnızca birkaç bileşen üst konumu belirlemek için yeterli olduğunda etkilidir. Kitaplık Ayrıca, genelleştirilmiş Unitary ile bağlanmış küme ANSATZ aracılığıyla tek bir temelinde başvurunun üzerine dinamik bağıntılar dahil etmek için bir yöntem sağlar. Ayrıca, bu durumlar için bir hisse bilgisayarında bu durumları oluşturan hisse devreleri de oluşturur. Bu durumlar [broombridge şemasında](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)belirlenebilir ve ayrıca bu durumları Kimya kitaplığı aracılığıyla el ile belirtme işlevlerini de sağlarız.

## <a name="sparse-multi-reference-wavefunction"></a>Seyrek Multi-Reference wavefunction
Çok başvurulu bir durum $ \ket{\ psi_ {\rm {MCSCF}}} $ açıkça $N $-elektron sdaha belirleyici bir şekilde doğrusal bir bileşim olarak belirtilebilir.
\begin{hizalaması} \ket{\ psi_ {\rm {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cnoktalar < i_N} \ lambda_ {i_1, i_2, \cnoktalar, i_N} a ^ \ dagger_ {İ_1} a ^ \ dagger_ {i_2} \tıı {0} .
\end{hizalaması} Örneğin, $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) {0} \tus$, aşağıdaki gibi kimya kitaplığında belirtilebilir.
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
Üst konum bileşenlerinin bu açık gösterimi yalnızca birkaç bileşenin belirtilmesi gerektiğinde etkilidir. İstenen durumu doğru bir şekilde yakalamak için birçok bileşen gerektiğinde bu gösterimi kullanmaktan kaçının. Bunun nedeni, bu durumu bir hisse bilgisayar üzerinde hazırlayan, en az üst konum bileşenleri ile en az doğrusal bir şekilde ölçeklendirilen ve üst konum güçlerinin tek bir norm ile en fazla çeyrek bir şekilde ölçeklendirilebilen, hisse başında bu durumu sağlayan geçit 'in bulunduğu kapı maliyetidir.

## <a name="unitary-coupled-cluster-wavefunction"></a>Unitary ile bağlanmış küme wavefunction
Ayrıca, bir Unitary ile bağlanmış küme wavefunction $ \ket{\ psi_ {\rm {UCC}}} $, chemistery kitaplığını kullanarak belirtilebilir. Bu durumda, tek bir determinantik başvuru durumuna sahip olduğumuz $ \ket{\ psi_ {\rm{SCF}}} $. Unitary ile bağlanmış küme dalga işlevinin bileşenleri, bir başvuru durumunda işlem gören Unitary operatörü aracılığıyla implicity belirtilir.
Bu Unitary işleci genellikle $e ^ {T-T ^ \abger} $ olarak yazılmıştır; burada $T-T ^ \dağılım $, Anti-hermitian küme operatöründür. Bu nedenle \begin{hizalaması} \ket{\ psi_ {\rm {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\Rm{SCF}}}.
\end{hizalaması}

Ayrıca, $T = T_1 + T_2 + \cnoktalar $ Cluster işlecinin parçalara bölünmesi, her parça $T _j $ gövde terimlerini $j. Genelleştirilmiş bağlanmış küme teorik 'inde, tek gövde küme operatörü (Singles), \begin{hizalaması} T_1 = \ sum_ {PQ} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{hizalaması} biçiminde

ve iki gövdede küme işleci (Double 'lar), \begin{hizalaması} T_2 = \ sum_ {pqrs} T ^ {PQ} _ {RS}. dagger_p bir ^ \ dagger_q a_r a_s.
\end{hizalaması}

Daha yüksek sıralı terimler (üçlü ve çeyrek Rupisi, vb.) mümkündür, ancak şu anda Kimya kitaplığı tarafından desteklenmiyor.

Örneğin, $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 a ^ \ dagger_2 {0} \tus$ ve dagger_0 $T = 0,123 a ^ \ A_1 dagger_0a + 0,456 0,789 a ^ \ dagger_3 ^ \ A_1 a_2 dagger_3a $. Bu durum, aşağıdaki gibi kimya kitaplığı 'nda oluşturulur.
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

Dönüş dönüştürmesi, `SpinOrbital` tamsayı dizinleri yerine dizinler belirtilerek açıkça yapılabilir. Örneğin psi_, < \ dagger_ {1, \upoklu} a ^ \ dagger_ {2, \downarrow}\ket {0} $ ve let $T = 0,123 a ^ \ dagger_ {0, \upoklu} a_ {1, \upoklu} + 0,456 a ^ \ dagger_ {0, \upoklu} a ^ \ dagger_ {3, \downok} a_ {1, \upoklu} a_ {2, \downconvserving}-0,789 a ^ \ dagger_ {3, \upoklu} dagger_ {1, \upoklu} a_,. Bu durum, aşağıdaki gibi kimya kitaplığı 'nda oluşturulur.
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

Ayrıca, Gamze 'nin yalnızca dönüş-yörünbitleri ve yalnızca dolu döndürme-orbitleri ile birlikte kapladığı küme işleçlerini numaralandırır.
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
