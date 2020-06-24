---
title: Dosyadan Hamiltonian yükleme
description: Broombridge şemasını kullanarak, büyük bir Hamiltonian 'ın otomatik olarak nasıl oluşturulacağını öğrenin.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
ms.openlocfilehash: 715dbcefc10ecc5af45f2bdd228890f1cb28886b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275247"
---
# <a name="loading-a-hamiltonian-from-file"></a>Dosyadan Hamiltonian yükleme
Daha önce, kendisine ayrı koşullar ekleyerek Hamiltonians oluşturduk. Bu küçük örnekler için çok iyi olsa da, ölçek at ölçeğinde hisse Hamiltonians, milyonlarca veya milyarlarca şart gerektirir. Nwchem gibi kimya paketleri tarafından oluşturulan Hamiltonians, el ile içeri aktarmak için çok büyük. Bu örnekte, bir `FermionHamiltonian` Örneğin, [Brombridge şeması](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)tarafından temsil edilen bir moleule tarafından otomatik olarak nasıl üretilebileceğinizi gösteririz. Başvuru için, bir tane, belirtilen `LithiumHydrideGUI` örneği veya `RunSimulation` örneği inceleyebilir. Sınırlı destek, [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/)tarafından tüketilen biçimden içeri aktarılmak için de kullanılabilir.

Örnek deposunun klasöründe sağlanan Nitrogen moleule örneğini görmemize izin verin `IntegralData/YAML` . Şemayı yükleme yöntemi `Broombridge` basittir.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Broombridge şeması, hazırlanan ilk durumun önerilerini de içerir. `"|G⟩"` `"|E1⟩"` Bu durumlar için, veya gibi Etiketler dosyayı inceleyerek görünebilir. Bu ilk durumları hazırlamak için, `qSharpData` Q # hisse algoritmaları tarafından tüketilen, [önceki bölüme](xref:microsoft.quantum.chemistry.examples.energyestimate)benzer şekilde alınır, ancak istenen ilk durumu seçerek ek bir parametreye sahip olur. Örneğin,
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Yukarıdaki tüm adımlar aşağıdaki gibi sunulan kullanışlı yöntemler kullanılarak kısaltılabilir.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

LIQUi bir Hamiltonian de yükleyebiliriz |> biçimi, çok benzer bir sözdizimi kullanılarak. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Bu işlemi herhangi bir Broombridge örneğinden veya herhangi bir ara adımın ardından, hisse aşamalı tahmin gibi hisse algoritmaları belirtilen elektronik yapı sorunu üzerinde çalıştırılabilir.
