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
# <a name="generatorindex-user-defined-type"></a><span data-ttu-id="56048-102">Generatorındex Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="56048-102">GeneratorIndex user defined type</span></span>

<span data-ttu-id="56048-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="56048-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="56048-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56048-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56048-105">Bu oluşturucunun, ile ilgili Oluşturucu tarafından zaman için bir eşleme varolduğu, örneğin, tüm dinamik oluşturucuları (ör. hermitian işleçleri) kümesinde tek bir temel terimi temsil eder `EvolutionSet` .</span><span class="sxs-lookup"><span data-stu-id="56048-105">Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.</span></span>

<span data-ttu-id="56048-106">İlk öğe (INT [], Double []) Tek terimli olan dizindir--Örneğin, 0,5 katsayısı olan Pauli dize XXY, ([1, 1, 2], [0,5]) tarafından dizinlenebilir.</span><span class="sxs-lookup"><span data-stu-id="56048-106">The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]).</span></span> <span data-ttu-id="56048-107">Alternatif olarak, X cos φ + Y φ gibi sürekli bir değişken tarafından parametreleştirilen Hamiltonians, örneğin ([], [φ]) tarafından temsil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="56048-107">Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]).</span></span> <span data-ttu-id="56048-108">İkinci öğe, oluşturucunun üzerinde çalıştığı alt sistemin dizinini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="56048-108">The second element indexes the subsystem on which the generator acts on.</span></span>

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a><span data-ttu-id="56048-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="56048-109">Example</span></span>

<span data-ttu-id="56048-110">Kullanarak  <xref:microsoft.quantum.simulation.paulievolutionset> , $ \pı X_2 X_5 Y_9 $ işleci şu şekilde gösterilir:</span><span class="sxs-lookup"><span data-stu-id="56048-110">Using  <xref:microsoft.quantum.simulation.paulievolutionset>, the operator $\pi X_2 X_5 Y_9$ is represented as:</span></span>

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a><span data-ttu-id="56048-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="56048-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="56048-112">' In yorumu, `GeneratorIndex` belirli bir dizi özel kümesine başvuru dışında tanımlı değildir.</span><span class="sxs-lookup"><span data-stu-id="56048-112">The interpretation of an `GeneratorIndex` is not defined except with reference to a particular set of generators.</span></span>

## <a name="see-also"></a><span data-ttu-id="56048-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="56048-113">See Also</span></span>

- [<span data-ttu-id="56048-114">Microsoft. hisse. simülasyon. EvolutionSet</span><span class="sxs-lookup"><span data-stu-id="56048-114">Microsoft.Quantum.Simulation.EvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [<span data-ttu-id="56048-115">Microsoft. hisse. simülasyon. PauliEvolutionSet</span><span class="sxs-lookup"><span data-stu-id="56048-115">Microsoft.Quantum.Simulation.PauliEvolutionSet</span></span>](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)