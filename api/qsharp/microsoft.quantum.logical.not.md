---
uid: Microsoft.Quantum.Logical.Not
title: Not işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197458"
---
# <a name="not-function"></a><span data-ttu-id="d291c-102">Not işlevi</span><span class="sxs-lookup"><span data-stu-id="d291c-102">Not function</span></span>

<span data-ttu-id="d291c-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d291c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d291c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d291c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d291c-105">Değerin Boole olumsuzunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="d291c-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d291c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d291c-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="d291c-107">değer: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d291c-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d291c-108">Değillenmiş değer.</span><span class="sxs-lookup"><span data-stu-id="d291c-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d291c-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d291c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d291c-110">`true` ve yalnızca ise `value` `false` .</span><span class="sxs-lookup"><span data-stu-id="d291c-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d291c-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d291c-111">Remarks</span></span>

<span data-ttu-id="d291c-112">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="d291c-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```