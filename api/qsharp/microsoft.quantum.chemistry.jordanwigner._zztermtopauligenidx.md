---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: f8a173e2adb4494a08b48158a010f264562bbaa6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727830"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="f0158-102">_ZZTermToPauliGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="f0158-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="f0158-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f0158-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f0158-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0158-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0158-105">Bir ZZ terimini, Paulıs açısından bir ' Generatorındex [] ' ifadesine tanıtan bir Generatorındex dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="f0158-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="f0158-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f0158-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="f0158-107">terim: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="f0158-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="f0158-108">`GeneratorIndex` bir ZZ terimini temsil eden.</span><span class="sxs-lookup"><span data-stu-id="f0158-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="f0158-109">Output: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="f0158-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="f0158-110">' Generatorındex [] ', ZZ terimini Pauli terimleri olarak ifade etme.</span><span class="sxs-lookup"><span data-stu-id="f0158-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>