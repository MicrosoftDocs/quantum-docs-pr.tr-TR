---
uid: Microsoft.Quantum.Chemistry.JordanWigner._PQandPQQRTermToPauliMajIdx_
title: _Pqandpqqrtermtopaulimajıdx_ işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _PQandPQQRTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 1a04f5f3b66e0dccb650b2d451a086a380b9810a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225015"
---
# <a name="_pqandpqqrtermtopaulimajidx_-function"></a><span data-ttu-id="74120-102">_Pqandpqqrtermtopaulimajıdx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="74120-102">_PQandPQQRTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="74120-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="74120-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="74120-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="74120-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="74120-105">PQ veya PQQR terimini tanımlayan bir Generatorındex öğesini Paulis bakımından ' Generatorındex [] ' ifadesine dönüştürür</span><span class="sxs-lookup"><span data-stu-id="74120-105">Converts a GeneratorIndex describing a PQ or PQQR term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _PQandPQQRTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="74120-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="74120-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="74120-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="74120-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="74120-108">`GeneratorIndex` PQ veya PQQR terimini temsil etme.</span><span class="sxs-lookup"><span data-stu-id="74120-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="74120-109">Çıkış: [Optimizedbesonlandırdex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="74120-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="74120-110">' Generatorındex [] ' PQ veya PQQR terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="74120-110">'GeneratorIndex[]' expressing PQ or PQQR term as Pauli terms.</span></span>