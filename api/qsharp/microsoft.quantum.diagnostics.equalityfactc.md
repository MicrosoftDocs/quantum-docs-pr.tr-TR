---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727248"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="be2e3-102">EqualityFactC işlevi</span><span class="sxs-lookup"><span data-stu-id="be2e3-102">EqualityFactC function</span></span>

<span data-ttu-id="be2e3-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="be2e3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="be2e3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be2e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be2e3-105">Karmaşık bir sayının beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="be2e3-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="be2e3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="be2e3-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="be2e3-107">gerçek: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="be2e3-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="be2e3-108">Denetlenecek değer.</span><span class="sxs-lookup"><span data-stu-id="be2e3-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="be2e3-109">beklenen: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="be2e3-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="be2e3-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="be2e3-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="be2e3-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="be2e3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="be2e3-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="be2e3-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be2e3-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be2e3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

