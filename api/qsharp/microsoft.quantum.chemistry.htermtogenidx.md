---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728129"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="26bc2-102">HTermToGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="26bc2-102">HTermToGenIdx function</span></span>

<span data-ttu-id="26bc2-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="26bc2-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="26bc2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26bc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26bc2-105">Veri biçimindeki Hamiltonian terimini `HTerm` bir Generatorındex öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="26bc2-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="26bc2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="26bc2-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="26bc2-107">terim: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="26bc2-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="26bc2-108">Verileri biçimde girin `HTerm` .</span><span class="sxs-lookup"><span data-stu-id="26bc2-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="26bc2-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="26bc2-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="26bc2-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="26bc2-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="26bc2-111">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="26bc2-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="26bc2-112">Tarafından temsil edilen bir Hamiltonian terimini `term` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .</span><span class="sxs-lookup"><span data-stu-id="26bc2-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>