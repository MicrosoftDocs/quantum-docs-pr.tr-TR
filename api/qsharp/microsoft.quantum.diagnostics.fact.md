---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Olgu işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727206"
---
# <a name="fact-function"></a><span data-ttu-id="8dbaf-102">Olgu işlevi</span><span class="sxs-lookup"><span data-stu-id="8dbaf-102">Fact function</span></span>

<span data-ttu-id="8dbaf-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8dbaf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8dbaf-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8dbaf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8dbaf-105">Klasik koşulun true olduğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="8dbaf-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8dbaf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8dbaf-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="8dbaf-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8dbaf-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8dbaf-108">Belirtilecek koşul.</span><span class="sxs-lookup"><span data-stu-id="8dbaf-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="8dbaf-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8dbaf-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8dbaf-110">Klasik koşulun yanlış olması durumunda yazdırılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="8dbaf-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8dbaf-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8dbaf-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8dbaf-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8dbaf-112">See Also</span></span>

- [<span data-ttu-id="8dbaf-113">Microsoft. hisse. tanılama. çelişme</span><span class="sxs-lookup"><span data-stu-id="8dbaf-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)