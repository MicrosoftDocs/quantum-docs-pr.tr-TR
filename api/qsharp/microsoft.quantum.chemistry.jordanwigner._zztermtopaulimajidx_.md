---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _Zztermtopaulimajidx_ işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 8c9223d54585f91e1616021bf0643e558d57589c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727824"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="07735-102">_Zztermtopaulimajidx_ işlevi</span><span class="sxs-lookup"><span data-stu-id="07735-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="07735-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="07735-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="07735-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07735-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07735-105">Bir ZZ terimini, Paulıs açısından bir ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="07735-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="07735-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="07735-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="07735-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="07735-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="07735-108">`GeneratorIndex` bir ZZ terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="07735-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="07735-109">Çıkış: [Optimizedbesonlandırdex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="07735-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="07735-110">' Generatorındex [] ', ZZ terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="07735-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>