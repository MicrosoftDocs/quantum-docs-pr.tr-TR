---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210072"
---
# <a name="constantarray-function"></a><span data-ttu-id="2a0f9-102">ConstantArray işlevi</span><span class="sxs-lookup"><span data-stu-id="2a0f9-102">ConstantArray function</span></span>

<span data-ttu-id="2a0f9-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2a0f9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2a0f9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a0f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a0f9-105">Verilen değere eşit tüm öğelerle verilen uzunlukta bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="2a0f9-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2a0f9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a0f9-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="2a0f9-107">Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a0f9-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a0f9-108">Yeni dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="2a0f9-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="2a0f9-109">değer: 'T</span><span class="sxs-lookup"><span data-stu-id="2a0f9-109">value : 'T</span></span>

<span data-ttu-id="2a0f9-110">Yeni dizinin her öğesinin değeri.</span><span class="sxs-lookup"><span data-stu-id="2a0f9-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2a0f9-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="2a0f9-111">Output : 'T[]</span></span>

<span data-ttu-id="2a0f9-112">Her öğe için olan yeni bir uzunluk dizisi `length` `value` .</span><span class="sxs-lookup"><span data-stu-id="2a0f9-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2a0f9-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2a0f9-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a0f9-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2a0f9-114">'T</span></span>

