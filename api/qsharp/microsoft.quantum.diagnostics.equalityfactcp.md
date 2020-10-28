---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727242"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="3b50b-102">EqualityFactCP işlevi</span><span class="sxs-lookup"><span data-stu-id="3b50b-102">EqualityFactCP function</span></span>

<span data-ttu-id="3b50b-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3b50b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3b50b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b50b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b50b-105">Karmaşık bir sayının beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="3b50b-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3b50b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3b50b-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="3b50b-107">gerçek: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="3b50b-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="3b50b-108">Denetlenecek değer.</span><span class="sxs-lookup"><span data-stu-id="3b50b-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="3b50b-109">beklenen: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="3b50b-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="3b50b-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="3b50b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="3b50b-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3b50b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3b50b-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="3b50b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b50b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b50b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

