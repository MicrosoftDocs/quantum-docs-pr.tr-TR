---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Çelişme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727284"
---
# <a name="contradiction-function"></a><span data-ttu-id="fadfd-102">Çelişme işlevi</span><span class="sxs-lookup"><span data-stu-id="fadfd-102">Contradiction function</span></span>

<span data-ttu-id="fadfd-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fadfd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fadfd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fadfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fadfd-105">Klasik koşulun yanlış olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="fadfd-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fadfd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fadfd-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="fadfd-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fadfd-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fadfd-108">Belirtilecek koşul.</span><span class="sxs-lookup"><span data-stu-id="fadfd-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="fadfd-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fadfd-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fadfd-110">Klasik koşulun doğru olması durumunda yazdırılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="fadfd-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fadfd-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fadfd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="fadfd-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fadfd-112">See Also</span></span>

- [<span data-ttu-id="fadfd-113">Microsoft. hisse. Diagnostics. olgu</span><span class="sxs-lookup"><span data-stu-id="fadfd-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)