---
uid: Microsoft.Quantum.Simulation.IdxToUnitary
title: Idxtounitary işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToUnitary
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: a142d8a5af56a43de6341e3c0bdc77f50030f06e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726312"
---
# <a name="idxtounitary-function"></a><span data-ttu-id="e3a87-102">Idxtounitary işlevi</span><span class="sxs-lookup"><span data-stu-id="e3a87-102">IdxToUnitary function</span></span>

<span data-ttu-id="e3a87-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e3a87-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e3a87-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3a87-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3a87-105">Uygulamasında kullanılır `PauliBlockEncoding`</span><span class="sxs-lookup"><span data-stu-id="e3a87-105">Used in implementation of `PauliBlockEncoding`</span></span>

```qsharp
function IdxToUnitary (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToUnitary : (Microsoft.Quantum.Simulation.GeneratorIndex -> (Qubit[] => Unit is Adj + Ctl))) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e3a87-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e3a87-106">Input</span></span>

### <a name="idx--int"></a><span data-ttu-id="e3a87-107">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e3a87-107">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="genfun--int---generatorindex"></a><span data-ttu-id="e3a87-108">geneğlence: [Int](xref:microsoft.quantum.lang-ref.int) -> [generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e3a87-108">genFun : [Int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>




### <a name="genidxtounitary--generatorindex---qubit--unit-adj--ctl"></a><span data-ttu-id="e3a87-109">genıdxtounitary: [generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e3a87-109">genIdxToUnitary : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="e3a87-110">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e3a87-110">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="e3a87-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e3a87-111">See Also</span></span>

- [<span data-ttu-id="e3a87-112">Microsoft. hisse. simülasyon. Pauliblockenkodlama</span><span class="sxs-lookup"><span data-stu-id="e3a87-112">Microsoft.Quantum.Simulation.PauliBlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)