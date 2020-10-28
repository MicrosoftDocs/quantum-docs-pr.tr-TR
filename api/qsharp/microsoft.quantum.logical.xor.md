---
uid: Microsoft.Quantum.Logical.Xor
title: XOR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732815"
---
# <a name="xor-function"></a><span data-ttu-id="1834a-102">XOR işlevi</span><span class="sxs-lookup"><span data-stu-id="1834a-102">Xor function</span></span>

<span data-ttu-id="1834a-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1834a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1834a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1834a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1834a-105">İki değerin Boole dışlamalı bir ilişkisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1834a-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="1834a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1834a-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="1834a-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1834a-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1834a-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="1834a-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="1834a-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1834a-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1834a-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="1834a-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1834a-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1834a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1834a-112">`true` ve yalnızca tam olarak bir ve ise `a` `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="1834a-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>