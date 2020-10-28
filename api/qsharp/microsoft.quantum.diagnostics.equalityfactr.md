---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727230"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="2e3bb-102">EqualityFactR işlevi</span><span class="sxs-lookup"><span data-stu-id="2e3bb-102">EqualityFactR function</span></span>

<span data-ttu-id="2e3bb-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2e3bb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2e3bb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e3bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e3bb-105">Klasik bir sonuç değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2e3bb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2e3bb-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="2e3bb-107">gerçek: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e3bb-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="2e3bb-108">Denetlenecek değişken.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="2e3bb-109">beklenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="2e3bb-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="2e3bb-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="2e3bb-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2e3bb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2e3bb-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="2e3bb-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e3bb-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e3bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

