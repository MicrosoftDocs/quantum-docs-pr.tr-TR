---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Equalitywithıntoleranceolgu işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828743"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="2ffa5-102">Equalitywithıntoleranceolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="2ffa5-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="2ffa5-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2ffa5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ffa5-105">Bir klasik kayan nokta değerinin, belirtilen mutlak tolerans için beklenen değere sahip olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="2ffa5-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="2ffa5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2ffa5-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="2ffa5-107">gerçek: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ffa5-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="2ffa5-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="2ffa5-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ffa5-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="2ffa5-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="2ffa5-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ffa5-112">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="2ffa5-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ffa5-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ffa5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

