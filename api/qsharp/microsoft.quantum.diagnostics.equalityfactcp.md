---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: a207ba1c4d08ec58095f5db34ee32c7341002920
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829182"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="ddd48-102">EqualityFactCP işlevi</span><span class="sxs-lookup"><span data-stu-id="ddd48-102">EqualityFactCP function</span></span>

<span data-ttu-id="ddd48-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ddd48-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ddd48-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddd48-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddd48-105">Karmaşık bir sayının beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="ddd48-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ddd48-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ddd48-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="ddd48-107">gerçek: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ddd48-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ddd48-108">Denetlenecek değer.</span><span class="sxs-lookup"><span data-stu-id="ddd48-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="ddd48-109">beklenen: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="ddd48-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="ddd48-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="ddd48-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ddd48-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ddd48-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ddd48-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="ddd48-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddd48-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddd48-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

