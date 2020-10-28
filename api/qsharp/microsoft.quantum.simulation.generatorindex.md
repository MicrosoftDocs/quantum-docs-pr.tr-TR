---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Generatorındex Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733162"
---
# <a name="generatorindex-user-defined-type"></a>Generatorındex Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Bu oluşturucunun, ile ilgili Oluşturucu tarafından zaman için bir eşleme varolduğu, örneğin, tüm dinamik oluşturucuları (ör. hermitian işleçleri) kümesinde tek bir temel terimi temsil eder `EvolutionSet` .

İlk öğe (INT [], Double []) Tek terimli olan dizindir--Örneğin, 0,5 katsayısı olan Pauli dize XXY, ([1, 1, 2], [0,5]) tarafından dizinlenebilir. Alternatif olarak, X cos φ + Y φ gibi sürekli bir değişken tarafından parametreleştirilen Hamiltonians, örneğin ([], [φ]) tarafından temsil edilebilir. İkinci öğe, oluşturucunun üzerinde çalıştığı alt sistemin dizinini oluşturur.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> ' In yorumu, `GeneratorIndex` belirli bir dizi özel kümesine başvuru dışında tanımlı değildir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. hisse. simülasyon. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)