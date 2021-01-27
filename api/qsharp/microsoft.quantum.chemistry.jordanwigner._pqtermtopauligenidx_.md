---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliGenIdx_
title: _Pqtermtopauligenidx_ işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 046b3b7b78cee7f046607277896100e20c33a32d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839305"
---
# <a name="_pqtermtopauligenidx_-function"></a><span data-ttu-id="9d785-102">_Pqtermtopauligenidx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="9d785-102">_PQTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="9d785-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9d785-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9d785-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9d785-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="9d785-105">PQ terimini, Paulis bakımından ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex 'i dönüştürür</span><span class="sxs-lookup"><span data-stu-id="9d785-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="9d785-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9d785-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="9d785-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9d785-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9d785-108">`GeneratorIndex` PQ terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="9d785-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="9d785-109">Output: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="9d785-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="9d785-110">' Generatorındex [] ' PQ terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="9d785-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>