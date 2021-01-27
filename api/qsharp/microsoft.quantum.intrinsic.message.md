---
uid: Microsoft.Quantum.Intrinsic.Message
title: İleti işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849369"
---
# <a name="message-function"></a><span data-ttu-id="766a6-102">İleti işlevi</span><span class="sxs-lookup"><span data-stu-id="766a6-102">Message function</span></span>

<span data-ttu-id="766a6-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="766a6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="766a6-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="766a6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="766a6-105">Bir iletiyi günlüğe kaydeder.</span><span class="sxs-lookup"><span data-stu-id="766a6-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="766a6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="766a6-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="766a6-107">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="766a6-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="766a6-108">Raporlanacak ileti.</span><span class="sxs-lookup"><span data-stu-id="766a6-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="766a6-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="766a6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="766a6-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="766a6-110">Remarks</span></span>

<span data-ttu-id="766a6-111">Bu işlevin belirli davranışı Benzetici bağımlıdır, ancak çoğu durumda verilen ileti konsola yazılır.</span><span class="sxs-lookup"><span data-stu-id="766a6-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>