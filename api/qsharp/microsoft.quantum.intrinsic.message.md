---
uid: Microsoft.Quantum.Intrinsic.Message
title: İleti işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199023"
---
# <a name="message-function"></a><span data-ttu-id="c99f4-102">İleti işlevi</span><span class="sxs-lookup"><span data-stu-id="c99f4-102">Message function</span></span>

<span data-ttu-id="c99f4-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="c99f4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="c99f4-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c99f4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c99f4-105">Bir iletiyi günlüğe kaydeder.</span><span class="sxs-lookup"><span data-stu-id="c99f4-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="c99f4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c99f4-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="c99f4-107">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c99f4-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c99f4-108">Raporlanacak ileti.</span><span class="sxs-lookup"><span data-stu-id="c99f4-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c99f4-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c99f4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c99f4-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c99f4-110">Remarks</span></span>

<span data-ttu-id="c99f4-111">Bu işlevin belirli davranışı Benzetici bağımlıdır, ancak çoğu durumda verilen ileti konsola yazılır.</span><span class="sxs-lookup"><span data-stu-id="c99f4-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>