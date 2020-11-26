---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Olgu işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201691"
---
# <a name="fact-function"></a><span data-ttu-id="e70a7-102">Olgu işlevi</span><span class="sxs-lookup"><span data-stu-id="e70a7-102">Fact function</span></span>

<span data-ttu-id="e70a7-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e70a7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e70a7-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e70a7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e70a7-105">Klasik koşulun true olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="e70a7-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e70a7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e70a7-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e70a7-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e70a7-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e70a7-108">Belirtilecek koşul.</span><span class="sxs-lookup"><span data-stu-id="e70a7-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e70a7-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e70a7-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e70a7-110">Klasik koşulun yanlış olması durumunda yazdırılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="e70a7-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e70a7-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e70a7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e70a7-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e70a7-112">See Also</span></span>

- [<span data-ttu-id="e70a7-113">Microsoft. hisse. tanılama. çelişme</span><span class="sxs-lookup"><span data-stu-id="e70a7-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)