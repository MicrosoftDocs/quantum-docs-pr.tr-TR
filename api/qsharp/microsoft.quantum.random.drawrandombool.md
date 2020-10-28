---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730954"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="2a31b-102">DrawRandomBool işlemi</span><span class="sxs-lookup"><span data-stu-id="2a31b-102">DrawRandomBool operation</span></span>

<span data-ttu-id="2a31b-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="2a31b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="2a31b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a31b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a31b-105">Başarılı bir olasılık verildiğinde, verilen olasılığa sahip tek bir Bernoulli denemesi döndürür.</span><span class="sxs-lookup"><span data-stu-id="2a31b-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="2a31b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a31b-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="2a31b-107">Başarılı olasılık: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2a31b-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2a31b-108">`true`Döndürülecek olasılık.</span><span class="sxs-lookup"><span data-stu-id="2a31b-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2a31b-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2a31b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2a31b-110">`true` olasılık `successProbability` ve `false` olasılık `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="2a31b-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>