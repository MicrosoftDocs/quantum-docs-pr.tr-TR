---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Equalitywithıntoleranceolgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727235"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="01204-102">Equalitywithıntoleranceolgu işlevi</span><span class="sxs-lookup"><span data-stu-id="01204-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="01204-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="01204-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="01204-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01204-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01204-105">Bir klasik kayan nokta değerinin, belirtilen mutlak tolerans için beklenen değere sahip olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="01204-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="01204-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="01204-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="01204-107">gerçek: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01204-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01204-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="01204-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="01204-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01204-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01204-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="01204-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="01204-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01204-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01204-112">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="01204-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="01204-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="01204-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

