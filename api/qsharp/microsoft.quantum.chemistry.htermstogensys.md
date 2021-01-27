---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851772"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="f8a10-102">HTermsToGenSys işlevi</span><span class="sxs-lookup"><span data-stu-id="f8a10-102">HTermsToGenSys function</span></span>

<span data-ttu-id="f8a10-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8a10-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f8a10-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f8a10-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f8a10-105">Veri biçimindeki Hamiltonian `HTerm[]` bir GeneratorSystem öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="f8a10-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f8a10-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f8a10-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="f8a10-107">veri: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="f8a10-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="f8a10-108">Verileri biçimde girin `HTerm[]` .</span><span class="sxs-lookup"><span data-stu-id="f8a10-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="f8a10-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f8a10-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f8a10-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="f8a10-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f8a10-111">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f8a10-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f8a10-112">Girişin gösterdiği Hamiltonian 'yi temsil eden bir GeneratorSystem `data` .</span><span class="sxs-lookup"><span data-stu-id="f8a10-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>