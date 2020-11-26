---
uid: Microsoft.Quantum.Logical.Xor
title: XOR işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197101"
---
# <a name="xor-function"></a><span data-ttu-id="556d7-102">XOR işlevi</span><span class="sxs-lookup"><span data-stu-id="556d7-102">Xor function</span></span>

<span data-ttu-id="556d7-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="556d7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="556d7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="556d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="556d7-105">İki değerin Boole dışlamalı bir ilişkisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="556d7-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="556d7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="556d7-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="556d7-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="556d7-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="556d7-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="556d7-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="556d7-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="556d7-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="556d7-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="556d7-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="556d7-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="556d7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="556d7-112">`true` ve yalnızca tam olarak bir ve ise `a` `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="556d7-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>