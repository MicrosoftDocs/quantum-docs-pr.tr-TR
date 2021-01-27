---
uid: Microsoft.Quantum.Logical.Xor
title: XOR işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848446"
---
# <a name="xor-function"></a><span data-ttu-id="1ea41-102">XOR işlevi</span><span class="sxs-lookup"><span data-stu-id="1ea41-102">Xor function</span></span>

<span data-ttu-id="1ea41-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1ea41-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1ea41-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1ea41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1ea41-105">İki değerin Boole dışlamalı bir ilişkisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="1ea41-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="1ea41-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1ea41-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="1ea41-107">y: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1ea41-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1ea41-108">Göz önünde bulundurmanız için ilk değer.</span><span class="sxs-lookup"><span data-stu-id="1ea41-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="1ea41-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1ea41-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1ea41-110">Göz önünde bulundurmanız için ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="1ea41-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1ea41-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1ea41-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1ea41-112">`true` ve yalnızca tam olarak bir ve ise `a` `b` `true` .</span><span class="sxs-lookup"><span data-stu-id="1ea41-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>