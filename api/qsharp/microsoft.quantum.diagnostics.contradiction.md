---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Çelişme işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202150"
---
# <a name="contradiction-function"></a><span data-ttu-id="9a37a-102">Çelişme işlevi</span><span class="sxs-lookup"><span data-stu-id="9a37a-102">Contradiction function</span></span>

<span data-ttu-id="9a37a-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9a37a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9a37a-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9a37a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9a37a-105">Klasik koşulun yanlış olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="9a37a-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9a37a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9a37a-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="9a37a-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9a37a-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9a37a-108">Belirtilecek koşul.</span><span class="sxs-lookup"><span data-stu-id="9a37a-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="9a37a-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9a37a-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9a37a-110">Klasik koşulun doğru olması durumunda yazdırılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="9a37a-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a37a-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a37a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9a37a-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9a37a-112">See Also</span></span>

- [<span data-ttu-id="9a37a-113">Microsoft. hisse. Diagnostics. olgu</span><span class="sxs-lookup"><span data-stu-id="9a37a-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)