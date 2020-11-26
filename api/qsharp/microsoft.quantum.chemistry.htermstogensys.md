---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204122"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="c24e6-102">HTermsToGenSys işlevi</span><span class="sxs-lookup"><span data-stu-id="c24e6-102">HTermsToGenSys function</span></span>

<span data-ttu-id="c24e6-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c24e6-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="c24e6-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c24e6-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="c24e6-105">Veri biçimindeki Hamiltonian `HTerm[]` bir GeneratorSystem öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="c24e6-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="c24e6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c24e6-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="c24e6-107">veri: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="c24e6-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="c24e6-108">Verileri biçimde girin `HTerm[]` .</span><span class="sxs-lookup"><span data-stu-id="c24e6-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="c24e6-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c24e6-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c24e6-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="c24e6-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="c24e6-111">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="c24e6-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="c24e6-112">Girişin gösterdiği Hamiltonian 'yi temsil eden bir GeneratorSystem `data` .</span><span class="sxs-lookup"><span data-stu-id="c24e6-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>