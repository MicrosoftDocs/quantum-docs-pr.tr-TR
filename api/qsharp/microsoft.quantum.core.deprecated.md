---
uid: Microsoft.Quantum.Core.Deprecated
title: Kullanım dışı Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832077"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="a6e29-102">Kullanım dışı Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="a6e29-102">Deprecated user defined type</span></span>

<span data-ttu-id="a6e29-103">Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a6e29-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a6e29-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a6e29-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a6e29-105">Derleyiciyi tanınan bir tür veya çağrılabilir olarak işaretlemek için kullanılan öznitelik.</span><span class="sxs-lookup"><span data-stu-id="a6e29-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="a6e29-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="a6e29-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="a6e29-107">YeniAd: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a6e29-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a6e29-108">Bunun yerine kullanılacak türün tam adı veya çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="a6e29-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="a6e29-109">Bir tür veya çağrılabilir bir değiştirme olmadan kullanımdan kalkmışsa boş dizeye ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="a6e29-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>