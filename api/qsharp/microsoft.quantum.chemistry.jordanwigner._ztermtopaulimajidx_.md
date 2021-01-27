---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZTermToPauliMajIdx_
title: _Ztermtopaulimajidx_ işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 56de7b7b425b7d7c5830c15d7119fc1d0291d061
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839094"
---
# <a name="_ztermtopaulimajidx_-function"></a><span data-ttu-id="8faeb-102">_Ztermtopaulimajidx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="8faeb-102">_ZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="8faeb-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="8faeb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="8faeb-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="8faeb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="8faeb-105">Bir Z terimini, Paulıs açısından ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="8faeb-105">Converts a GeneratorIndex describing a Z term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="8faeb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8faeb-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="8faeb-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="8faeb-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="8faeb-108">`GeneratorIndex` Z terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="8faeb-108">`GeneratorIndex` representing a Z term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="8faeb-109">Çıkış: [Optimizedbesonlandırdex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="8faeb-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="8faeb-110">' Generatorındex [] ', Z terimini Pauli terimleri olarak ifade.</span><span class="sxs-lookup"><span data-stu-id="8faeb-110">'GeneratorIndex[]' expressing Z term as Pauli terms.</span></span>