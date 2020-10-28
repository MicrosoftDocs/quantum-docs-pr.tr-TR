---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730431"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="6e35d-102">_SwapOrderToPermuteArray işlevi</span><span class="sxs-lookup"><span data-stu-id="6e35d-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="6e35d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6e35d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6e35d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e35d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e35d-105">Sıralı bir dizi oluşturmak için bir dizideki sıralama öğelerinin takas edilmesi gereken sırası döndürür.</span><span class="sxs-lookup"><span data-stu-id="6e35d-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="6e35d-106">Değiştirmeleri bir yerde gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="6e35d-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="6e35d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="6e35d-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="6e35d-108">newOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6e35d-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6e35d-109">Yeni dizinin dizinlerinin permütasyoniyle dizi.</span><span class="sxs-lookup"><span data-stu-id="6e35d-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="6e35d-110">$N $ öğe olmalıdır, her biri $0 $ ile $n-$1 arasında benzersiz bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="6e35d-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="6e35d-111">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="6e35d-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="6e35d-112">Kayıt düzeni, takas edilecek iki dizini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="6e35d-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="6e35d-113">Takas eden en düşük dizinde başlar.</span><span class="sxs-lookup"><span data-stu-id="6e35d-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e35d-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6e35d-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="6e35d-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="6e35d-115">Psuedocode</span></span>

<span data-ttu-id="6e35d-116">için (Dizin 0.. length (newOrder)-1) {while newOrder [Dizin]! = Dizin {Switch newOrder [Dizin] ile newOrder [Dizin]]}}</span><span class="sxs-lookup"><span data-stu-id="6e35d-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>