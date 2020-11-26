---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216039"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="6821e-102">HTermToGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="6821e-102">HTermToGenIdx function</span></span>

<span data-ttu-id="6821e-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6821e-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="6821e-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6821e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6821e-105">Veri biçimindeki Hamiltonian terimini `HTerm` bir Generatorındex öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="6821e-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="6821e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6821e-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="6821e-107">terim: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="6821e-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="6821e-108">Verileri biçimde girin `HTerm` .</span><span class="sxs-lookup"><span data-stu-id="6821e-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6821e-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6821e-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6821e-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="6821e-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="6821e-111">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6821e-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6821e-112">Tarafından temsil edilen bir Hamiltonian terimini `term` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .</span><span class="sxs-lookup"><span data-stu-id="6821e-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>