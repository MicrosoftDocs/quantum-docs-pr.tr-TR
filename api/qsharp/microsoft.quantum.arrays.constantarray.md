---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846242"
---
# <a name="constantarray-function"></a><span data-ttu-id="945ad-102">ConstantArray işlevi</span><span class="sxs-lookup"><span data-stu-id="945ad-102">ConstantArray function</span></span>

<span data-ttu-id="945ad-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="945ad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="945ad-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="945ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="945ad-105">Verilen değere eşit tüm öğelerle verilen uzunlukta bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="945ad-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="945ad-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="945ad-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="945ad-107">Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="945ad-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="945ad-108">Yeni dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="945ad-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="945ad-109">değer: 'T</span><span class="sxs-lookup"><span data-stu-id="945ad-109">value : 'T</span></span>

<span data-ttu-id="945ad-110">Yeni dizinin her öğesinin değeri.</span><span class="sxs-lookup"><span data-stu-id="945ad-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="945ad-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="945ad-111">Output : 'T[]</span></span>

<span data-ttu-id="945ad-112">Her öğe için olan yeni bir uzunluk dizisi `length` `value` .</span><span class="sxs-lookup"><span data-stu-id="945ad-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="945ad-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="945ad-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="945ad-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="945ad-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="945ad-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="945ad-115">Example</span></span>

<span data-ttu-id="945ad-116">Aşağıdaki kod, her biri şuna eşit olan 3 Boole değeri dizisi oluşturur `true` :</span><span class="sxs-lookup"><span data-stu-id="945ad-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```