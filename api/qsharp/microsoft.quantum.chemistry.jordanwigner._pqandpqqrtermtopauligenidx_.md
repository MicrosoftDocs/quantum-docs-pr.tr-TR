---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliGenIdx_
title: _Pqandpqqrtermtopauligenidx_ işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 17acd2c09129275af90222e30fd96a7551e18b50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203544"
---
# <a name="_pqandpqqrtermtopauligenidx_-function"></a><span data-ttu-id="1541d-102">_Pqandpqqrtermtopauligenidx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="1541d-102">_PQandPQQRTermToPauliGenIdx_ function</span></span>

<span data-ttu-id="1541d-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1541d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1541d-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1541d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1541d-105">PQ veya PQQR terimini tanımlayan bir Generatorındex öğesini Paulis bakımından ' Generatorındex [] ' ifadesine dönüştürür</span><span class="sxs-lookup"><span data-stu-id="1541d-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="1541d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1541d-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="1541d-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="1541d-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="1541d-108">`GeneratorIndex` PQ veya PQQR terimini temsil etme.</span><span class="sxs-lookup"><span data-stu-id="1541d-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="1541d-109">Output: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="1541d-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="1541d-110">' Generatorındex [] ' PQ veya PQQR terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="1541d-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>