---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 46745632e2f6bafad0d7359141522b84f48c039d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839609"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="adf08-102">HTermToGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="adf08-102">HTermToGenIdx function</span></span>

<span data-ttu-id="adf08-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="adf08-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="adf08-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="adf08-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="adf08-105">Veri biçimindeki Hamiltonian terimini `HTerm` bir Generatorındex öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="adf08-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="adf08-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="adf08-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="adf08-107">terim: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="adf08-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="adf08-108">Verileri biçimde girin `HTerm` .</span><span class="sxs-lookup"><span data-stu-id="adf08-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="adf08-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="adf08-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="adf08-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="adf08-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="adf08-111">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="adf08-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="adf08-112">Tarafından temsil edilen bir Hamiltonian terimini `term` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .</span><span class="sxs-lookup"><span data-stu-id="adf08-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>