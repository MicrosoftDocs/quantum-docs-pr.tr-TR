---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727193"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="67bb3-102">NearEqualityFactD işlevi</span><span class="sxs-lookup"><span data-stu-id="67bb3-102">NearEqualityFactD function</span></span>

<span data-ttu-id="67bb3-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="67bb3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="67bb3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="67bb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="67bb3-105">Klasik bir kayan nokta değerinin, 1e-10 ' un küçük bir toleransına kadar beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="67bb3-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="67bb3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="67bb3-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="67bb3-107">gerçek: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67bb3-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67bb3-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="67bb3-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="67bb3-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="67bb3-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="67bb3-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="67bb3-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67bb3-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67bb3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="67bb3-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="67bb3-112">Remarks</span></span>

<span data-ttu-id="67bb3-113">Bu, <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ sabit kodlanmış toleransı ile eşdeğerdir {-10} .</span><span class="sxs-lookup"><span data-stu-id="67bb3-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>