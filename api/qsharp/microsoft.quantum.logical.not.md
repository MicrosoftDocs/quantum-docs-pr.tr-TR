---
uid: Microsoft.Quantum.Logical.Not
title: Not işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849082"
---
# <a name="not-function"></a><span data-ttu-id="4f69b-102">Not işlevi</span><span class="sxs-lookup"><span data-stu-id="4f69b-102">Not function</span></span>

<span data-ttu-id="4f69b-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4f69b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4f69b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f69b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f69b-105">Değerin Boole olumsuzunu döndürür.</span><span class="sxs-lookup"><span data-stu-id="4f69b-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="4f69b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4f69b-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="4f69b-107">değer: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f69b-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f69b-108">Değillenmiş değer.</span><span class="sxs-lookup"><span data-stu-id="4f69b-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4f69b-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4f69b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4f69b-110">`true` ve yalnızca ise `value` `false` .</span><span class="sxs-lookup"><span data-stu-id="4f69b-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f69b-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4f69b-111">Remarks</span></span>

<span data-ttu-id="4f69b-112">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4f69b-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```