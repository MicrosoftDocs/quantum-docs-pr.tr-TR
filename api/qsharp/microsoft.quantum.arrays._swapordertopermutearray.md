---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846285"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="a69a4-102">_SwapOrderToPermuteArray işlevi</span><span class="sxs-lookup"><span data-stu-id="a69a4-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="a69a4-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a69a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a69a4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a69a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a69a4-105">Sıralı bir dizi oluşturmak için bir dizideki sıralama öğelerinin takas edilmesi gereken sırası döndürür.</span><span class="sxs-lookup"><span data-stu-id="a69a4-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="a69a4-106">Değiştirmeleri bir yerde gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="a69a4-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="a69a4-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="a69a4-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="a69a4-108">newOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a69a4-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a69a4-109">Yeni dizinin dizinlerinin permütasyoniyle dizi.</span><span class="sxs-lookup"><span data-stu-id="a69a4-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="a69a4-110">$N $ öğe olmalıdır, her biri $0 $ ile $n-$1 arasında benzersiz bir tamsayıdır.</span><span class="sxs-lookup"><span data-stu-id="a69a4-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="a69a4-111">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a69a4-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="a69a4-112">Kayıt düzeni, takas edilecek iki dizini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a69a4-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="a69a4-113">Takas eden en düşük dizinde başlar.</span><span class="sxs-lookup"><span data-stu-id="a69a4-113">The swaps begin at the lowest index.</span></span>

## <a name="example"></a><span data-ttu-id="a69a4-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="a69a4-114">Example</span></span>

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a><span data-ttu-id="a69a4-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a69a4-115">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="a69a4-116">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="a69a4-116">Psuedocode</span></span>

<span data-ttu-id="a69a4-117">için (Dizin 0.. length (newOrder)-1) {while newOrder [Dizin]! = Dizin {Switch newOrder [Dizin] ile newOrder [Dizin]]}}</span><span class="sxs-lookup"><span data-stu-id="a69a4-117">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>