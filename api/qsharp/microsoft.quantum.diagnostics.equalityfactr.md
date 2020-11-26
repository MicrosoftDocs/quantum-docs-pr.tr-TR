---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201776"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="52684-102">EqualityFactR işlevi</span><span class="sxs-lookup"><span data-stu-id="52684-102">EqualityFactR function</span></span>

<span data-ttu-id="52684-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="52684-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="52684-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52684-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52684-105">Klasik bir sonuç değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="52684-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="52684-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="52684-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="52684-107">gerçek: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="52684-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="52684-108">Denetlenecek değişken.</span><span class="sxs-lookup"><span data-stu-id="52684-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="52684-109">beklenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="52684-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="52684-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="52684-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="52684-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="52684-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="52684-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="52684-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52684-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52684-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

