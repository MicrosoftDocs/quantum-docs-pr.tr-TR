---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853345"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="90b29-102">EqualityFactI işlevi</span><span class="sxs-lookup"><span data-stu-id="90b29-102">EqualityFactI function</span></span>

<span data-ttu-id="90b29-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="90b29-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="90b29-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90b29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90b29-105">Klasik bir INT değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="90b29-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="90b29-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="90b29-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="90b29-107">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90b29-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90b29-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="90b29-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="90b29-109">beklenen: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90b29-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90b29-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="90b29-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="90b29-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="90b29-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="90b29-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="90b29-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90b29-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90b29-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

