---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853685"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="cdc0c-102">DrawRandomBool işlemi</span><span class="sxs-lookup"><span data-stu-id="cdc0c-102">DrawRandomBool operation</span></span>

<span data-ttu-id="cdc0c-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cdc0c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cdc0c-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cdc0c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cdc0c-105">Başarılı bir olasılık verildiğinde, verilen olasılığa sahip tek bir Bernoulli denemesi döndürür.</span><span class="sxs-lookup"><span data-stu-id="cdc0c-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="cdc0c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cdc0c-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="cdc0c-107">Başarılı olasılık: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cdc0c-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cdc0c-108">`true`Döndürülecek olasılık.</span><span class="sxs-lookup"><span data-stu-id="cdc0c-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cdc0c-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cdc0c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cdc0c-110">`true` olasılık `successProbability` ve `false` olasılık `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="cdc0c-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="cdc0c-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="cdc0c-111">Example</span></span>

<span data-ttu-id="cdc0c-112">Aşağıdaki Q # kod parçacığı örnekleri, taraflı bir para ile döndürülür:</span><span class="sxs-lookup"><span data-stu-id="cdc0c-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```