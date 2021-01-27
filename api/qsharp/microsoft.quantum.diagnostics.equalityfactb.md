---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829217"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="ef890-102">EqualityFactB işlevi</span><span class="sxs-lookup"><span data-stu-id="ef890-102">EqualityFactB function</span></span>

<span data-ttu-id="ef890-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ef890-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ef890-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef890-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef890-105">Klasik bir bool değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="ef890-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ef890-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ef890-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="ef890-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ef890-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ef890-108">Denetlenecek değişken.</span><span class="sxs-lookup"><span data-stu-id="ef890-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="ef890-109">beklenen: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ef890-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ef890-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="ef890-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ef890-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ef890-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ef890-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="ef890-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ef890-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ef890-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

