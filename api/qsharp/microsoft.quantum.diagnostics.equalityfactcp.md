---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201861"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="a2b1a-102">EqualityFactCP işlevi</span><span class="sxs-lookup"><span data-stu-id="a2b1a-102">EqualityFactCP function</span></span>

<span data-ttu-id="a2b1a-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a2b1a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2b1a-105">Karmaşık bir sayının beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="a2b1a-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a2b1a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a2b1a-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="a2b1a-107">gerçek: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a2b1a-108">Denetlenecek değer.</span><span class="sxs-lookup"><span data-stu-id="a2b1a-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="a2b1a-109">beklenen: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a2b1a-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="a2b1a-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="a2b1a-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a2b1a-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="a2b1a-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2b1a-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2b1a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

