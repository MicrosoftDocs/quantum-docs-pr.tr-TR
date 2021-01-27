---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827903"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="625c0-102">NearEqualityFactD işlevi</span><span class="sxs-lookup"><span data-stu-id="625c0-102">NearEqualityFactD function</span></span>

<span data-ttu-id="625c0-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="625c0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="625c0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="625c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="625c0-105">Klasik bir kayan nokta değerinin, 1e-10 ' un küçük bir toleransına kadar beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="625c0-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="625c0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="625c0-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="625c0-107">gerçek: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="625c0-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="625c0-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="625c0-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="625c0-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="625c0-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="625c0-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="625c0-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="625c0-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="625c0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="625c0-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="625c0-112">Remarks</span></span>

<span data-ttu-id="625c0-113">Bu, <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ sabit kodlanmış toleransı ile eşdeğerdir {-10} .</span><span class="sxs-lookup"><span data-stu-id="625c0-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>