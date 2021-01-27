---
uid: Microsoft.Quantum.Chemistry.JordanWigner._V0123TermToPauliGenIdx_
title: _V0123TermToPauliGenIdx_ işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _V0123TermToPauliGenIdx_
qsharp.summary: Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis
ms.openlocfilehash: 8893d7c5479409a0ff98aa0b9e58f34fd3d274f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839184"
---
# <a name="_v0123termtopauligenidx_-function"></a><span data-ttu-id="3c65a-102">_V0123TermToPauliGenIdx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="3c65a-102">_V0123TermToPauliGenIdx_ function</span></span>

<span data-ttu-id="3c65a-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="3c65a-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="3c65a-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3c65a-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="3c65a-105">Bir PQRS terimini, Paulıs açısından ' Generatorındex [] ' ifadesine dönüştüren bir Generatorındex</span><span class="sxs-lookup"><span data-stu-id="3c65a-105">Converts a GeneratorIndex describing a PQRS term to an expression 'GeneratorIndex[]' in terms of Paulis</span></span>

```qsharp
function _V0123TermToPauliGenIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="3c65a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3c65a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="3c65a-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="3c65a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="3c65a-108">`GeneratorIndex` PQRS terimini temsil etme.</span><span class="sxs-lookup"><span data-stu-id="3c65a-108">`GeneratorIndex` representing a PQRS term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="3c65a-109">Output: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="3c65a-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="3c65a-110">' Generatorındex [] ', PQRS terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="3c65a-110">'GeneratorIndex[]' expressing PQRS term as Pauli terms.</span></span>