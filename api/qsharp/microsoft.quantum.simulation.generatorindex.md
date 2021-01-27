---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Generatorındex Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858374"
---
# <a name="generatorindex-user-defined-type"></a>Generatorındex Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu oluşturucunun, ile ilgili Oluşturucu tarafından zaman için bir eşleme varolduğu, örneğin, tüm dinamik oluşturucuları (ör. hermitian işleçleri) kümesinde tek bir temel terimi temsil eder `EvolutionSet` .

İlk öğe (INT [], Double []) Tek terimli olan dizindir--Örneğin, 0,5 katsayısı olan Pauli dize XXY, ([1, 1, 2], [0,5]) tarafından dizinlenebilir. Alternatif olarak, X cos φ + Y φ gibi sürekli bir değişken tarafından parametreleştirilen Hamiltonians, örneğin ([], [φ]) tarafından temsil edilebilir. İkinci öğe, oluşturucunun üzerinde çalıştığı alt sistemin dizinini oluşturur.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Örnek

Kullanarak  <xref:microsoft.quantum.simulation.paulievolutionset> , $ \pı X_2 X_5 Y_9 $ işleci şu şekilde gösterilir:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Açıklamalar

> [!WARNING]
> ' In yorumu, `GeneratorIndex` belirli bir dizi özel kümesine başvuru dışında tanımlı değildir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. hisse. simülasyon. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)