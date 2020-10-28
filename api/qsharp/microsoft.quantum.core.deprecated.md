---
uid: Microsoft.Quantum.Core.Deprecated
title: Kullanım dışı Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727458"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="e95d0-102">Kullanım dışı Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="e95d0-102">Deprecated user defined type</span></span>

<span data-ttu-id="e95d0-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="e95d0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="e95d0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e95d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e95d0-105">Derleyiciyi tanınan bir tür veya çağrılabilir olarak işaretlemek için kullanılan öznitelik.</span><span class="sxs-lookup"><span data-stu-id="e95d0-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="e95d0-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="e95d0-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="e95d0-107">YeniAd: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e95d0-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e95d0-108">Bunun yerine kullanılacak türün tam adı veya çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="e95d0-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="e95d0-109">Bir tür veya çağrılabilir bir değiştirme olmadan kullanımdan kalkmışsa boş dizeye ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="e95d0-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>