---
title: Symmetries of Molesel Integrals | Microsoft Docs
description: Symmetries of Molesel Integralleri kavramsal docs
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442385"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries of Molesel Integrals

[Elektronik sistemler Için hisse](xref:microsoft.quantum.chemistry.concepts.quantummodels)anlarca ve nuclei ile karşı elektrikle etkileşim kuran ve nuclei ile birlikte çalışan elektriksel 'In bulunduğu Coulomb Hamiltonian 'ın devralınan sifreu, bir dizi symmetries Hamiltonian 'daki terimleri sıkıştırmak için bu açıktan yararlanılabilir.
Genel olarak, $ \psı_j $ işlevleri hakkında daha fazla varsayım yapılmamadığımızda, yalnızca bu \begin{Equation} h_ {pqrs} = h_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation} [olduğundan, ](xref:microsoft.quantum.chemistry.concepts.quantummodels)$P, q $ ve $r, s $ ' den Anti-commutation ' d a ınterdeğiştiyse,, değerlerinin özdeş kalacağını belirten elektronik sistemler.

Döndürme-yörünge 'lerin gerçek değerli olduğunu varsaydığımızda (Gauss orbisi tabanlarında olduğu gibi), \ Begin{Equation} h_ {pqrs} = h_ {qpsr} = h_ {srqp} = h_ {rspq} = h_ {rqps} = h_ {psrq} = h_ {SPQR} = h_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{ Denklem} bu tür varsayımlar yaparken, Hamiltonian 'ın matris öğelerini $8 $; faktörü ile depolamak için gereken verileri azaltmak için yukarıdaki symmetries kullanabiliriz. Bunu yapmak, verilerin tutarlı bir şekilde daha zorlayıcı bir şekilde aktarılmasını sağlar.
Neyse ki Hamiltonian simülasyon kitaplığı, tamsayı dosyalarını [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) öğesinden veya doğrudan [nwchem](http://www.nwchem-sw.org/index.php/Main_Page)'den içe aktarmak için kullanılabilecek alt yordamlar içerir.

Molesel orbte integrals (örneğin, $h\_{PQ} $ ve $h\_{pqrs} $ terimleri), Bu simetriyi ifade etmek için bir dizi yararlı işlev sağlayan `OrbitalIntegral` türü kullanılarak temsil edilir.
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

Sayısal olarak özdeş olan tüm orbte integrallerden birinin numaralandırıldığı ek olarak, bir `OrbitalIntegral` tarafından temsil edilen Hafretonian içindeki tüm dönüş-orbte dizinlerinin bir listesi aşağıdaki gibi oluşturulabilir.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Molesel Integrallerden Fermıonic Hamiltonians oluşturma

`FermionTerm`s ekleyerek Fermionic Hamiltonian oluşturmak yerine, her bir orblik integrali 'e karşılık gelen tüm terimler otomatik olarak eklenebilir.
Örneğin, aşağıdaki kod, tüm perdeğiştirici symmetries üzerinde otomatik olarak numaralandırılır ve terimleri kurallı sırayla sıralar: 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```