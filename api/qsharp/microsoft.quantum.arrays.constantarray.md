---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730378"
---
# <a name="constantarray-function"></a><span data-ttu-id="64dc2-102">ConstantArray işlevi</span><span class="sxs-lookup"><span data-stu-id="64dc2-102">ConstantArray function</span></span>

<span data-ttu-id="64dc2-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="64dc2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="64dc2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64dc2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64dc2-105">Verilen değere eşit tüm öğelerle verilen uzunlukta bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="64dc2-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="64dc2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="64dc2-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="64dc2-107">Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="64dc2-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="64dc2-108">Yeni dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="64dc2-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="64dc2-109">değer: 'T</span><span class="sxs-lookup"><span data-stu-id="64dc2-109">value : 'T</span></span>

<span data-ttu-id="64dc2-110">Yeni dizinin her öğesinin değeri.</span><span class="sxs-lookup"><span data-stu-id="64dc2-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="64dc2-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="64dc2-111">Output : 'T[]</span></span>

<span data-ttu-id="64dc2-112">Her öğe için olan yeni bir uzunluk dizisi `length` `value` .</span><span class="sxs-lookup"><span data-stu-id="64dc2-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="64dc2-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="64dc2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64dc2-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="64dc2-114">'T</span></span>

