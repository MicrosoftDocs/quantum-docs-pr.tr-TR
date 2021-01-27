---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 84dc132528f8fd1c45fb2f7345111a05626ee686
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839626"
---
# <a name="htermstogenidx-function"></a><span data-ttu-id="41cdc-102">HTermsToGenIdx işlevi</span><span class="sxs-lookup"><span data-stu-id="41cdc-102">HTermsToGenIdx function</span></span>

<span data-ttu-id="41cdc-103">Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="41cdc-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="41cdc-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="41cdc-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="41cdc-105">Bir dizini, veri biçimindeki Hamiltonian terimine `HTerm[]` bir Generatorındex olarak dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="41cdc-105">Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="41cdc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="41cdc-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="41cdc-107">veri: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="41cdc-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="41cdc-108">Verileri biçimde girin `HTerm[]` .</span><span class="sxs-lookup"><span data-stu-id="41cdc-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="41cdc-109">termType: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="41cdc-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="41cdc-110">Generatorındex 'e ek bilgiler eklendi.</span><span class="sxs-lookup"><span data-stu-id="41cdc-110">Additional information added to GeneratorIndex.</span></span>


### <a name="idx--int"></a><span data-ttu-id="41cdc-111">idx: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="41cdc-111">idx : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="41cdc-112">Hamiltonian 'nin bir teriminin dizini</span><span class="sxs-lookup"><span data-stu-id="41cdc-112">Index to a term of the Hamiltonian</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="41cdc-113">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="41cdc-113">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="41cdc-114">Tarafından temsil edilen bir Hamiltonian terimini `data[idx]` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .</span><span class="sxs-lookup"><span data-stu-id="41cdc-114">A GeneratorIndex representing a Hamiltonian term represented by `data[idx]`, together with additional information added by `termType`.</span></span>