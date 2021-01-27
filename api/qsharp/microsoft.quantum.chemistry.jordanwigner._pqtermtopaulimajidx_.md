---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQTermToPauliMajIdx_
title: _Pqtermtopaulimajidx_ işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: edb9302e04de2abc6dfa9da0da27504f776e721f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839298"
---
# <a name="_pqtermtopaulimajidx_-function"></a><span data-ttu-id="33e7f-102">_Pqtermtopaulimajidx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="33e7f-102">_PQTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="33e7f-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="33e7f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="33e7f-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="33e7f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="33e7f-105">PQ terimini, Paulis bakımından ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex 'i dönüştürür</span><span class="sxs-lookup"><span data-stu-id="33e7f-105">Converts a GeneratorIndex describing a PQ term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="33e7f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="33e7f-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="33e7f-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="33e7f-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="33e7f-108">`GeneratorIndex` PQ terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="33e7f-108">`GeneratorIndex` representing a PQ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="33e7f-109">Çıkış: [Optimizedbesonlandırdex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="33e7f-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="33e7f-110">' Generatorındex [] ' PQ terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="33e7f-110">'GeneratorIndex[]' expressing PQ term as Pauli terms.</span></span>