---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223893"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="c177d-102">AllEqualityFactI işlevi</span><span class="sxs-lookup"><span data-stu-id="c177d-102">AllEqualityFactI function</span></span>

<span data-ttu-id="c177d-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c177d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c177d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c177d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c177d-105">İki tamsayı değeri dizilerinin eşit olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="c177d-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c177d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c177d-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="c177d-107">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c177d-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c177d-108">İlgilendiğiniz bir test çalışması tarafından üretilen dizi.</span><span class="sxs-lookup"><span data-stu-id="c177d-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="c177d-109">beklenen: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c177d-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c177d-110">İlgilendiğiniz test durumundan beklenen dizi.</span><span class="sxs-lookup"><span data-stu-id="c177d-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="c177d-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c177d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c177d-112">Diziler eşit değilse yazdırılacak bir ileti.</span><span class="sxs-lookup"><span data-stu-id="c177d-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c177d-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c177d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

