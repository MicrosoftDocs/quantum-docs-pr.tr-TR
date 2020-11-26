---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201844"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="ebeed-102">EqualityFactI işlevi</span><span class="sxs-lookup"><span data-stu-id="ebeed-102">EqualityFactI function</span></span>

<span data-ttu-id="ebeed-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ebeed-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ebeed-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ebeed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ebeed-105">Klasik bir INT değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="ebeed-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ebeed-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ebeed-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="ebeed-107">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebeed-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebeed-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="ebeed-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="ebeed-109">beklenen: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ebeed-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ebeed-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="ebeed-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ebeed-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ebeed-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ebeed-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="ebeed-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ebeed-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ebeed-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

