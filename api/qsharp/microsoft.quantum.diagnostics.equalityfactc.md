---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201912"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="24cb9-102">EqualityFactC işlevi</span><span class="sxs-lookup"><span data-stu-id="24cb9-102">EqualityFactC function</span></span>

<span data-ttu-id="24cb9-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="24cb9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="24cb9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24cb9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24cb9-105">Karmaşık bir sayının beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="24cb9-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="24cb9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="24cb9-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="24cb9-107">gerçek: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="24cb9-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="24cb9-108">Denetlenecek değer.</span><span class="sxs-lookup"><span data-stu-id="24cb9-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="24cb9-109">beklenen: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="24cb9-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="24cb9-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="24cb9-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="24cb9-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="24cb9-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="24cb9-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="24cb9-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24cb9-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24cb9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

