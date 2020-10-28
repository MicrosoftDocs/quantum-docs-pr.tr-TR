---
uid: Microsoft.Quantum.Intrinsic.Message
title: İleti işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726666"
---
# <a name="message-function"></a><span data-ttu-id="ea43e-102">İleti işlevi</span><span class="sxs-lookup"><span data-stu-id="ea43e-102">Message function</span></span>

<span data-ttu-id="ea43e-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ea43e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ea43e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea43e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea43e-105">Bir iletiyi günlüğe kaydeder.</span><span class="sxs-lookup"><span data-stu-id="ea43e-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ea43e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ea43e-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="ea43e-107">Msg: [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ea43e-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ea43e-108">Raporlanacak ileti.</span><span class="sxs-lookup"><span data-stu-id="ea43e-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea43e-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea43e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ea43e-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ea43e-110">Remarks</span></span>

<span data-ttu-id="ea43e-111">Bu işlevin belirli davranışı Benzetici bağımlıdır, ancak çoğu durumda verilen ileti konsola yazılır.</span><span class="sxs-lookup"><span data-stu-id="ea43e-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>