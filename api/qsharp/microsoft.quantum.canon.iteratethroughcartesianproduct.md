---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206452"
---
# <a name="iteratethroughcartesianproduct-operation"></a><span data-ttu-id="d7818-102">IterateThroughCartesianProduct işlemi</span><span class="sxs-lookup"><span data-stu-id="d7818-102">IterateThroughCartesianProduct operation</span></span>

<span data-ttu-id="d7818-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d7818-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d7818-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7818-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7818-105">Birkaç aralığın Kartezyen üründeki her bir dizin için bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="d7818-105">Applies an operation for each index in the Cartesian product of several ranges.</span></span>

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="d7818-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d7818-106">Description</span></span>

<span data-ttu-id="d7818-107">Yinelemeli olarak,,, `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` ,..., Kartezyen ürünün her bir öğesi için bir işlem uygular `0..(bounds[Length(bounds) - 1] - 1)`</span><span class="sxs-lookup"><span data-stu-id="d7818-107">Iteratively applies an operation for each element of the Cartesian product of `0..(bounds[0] - 1)`, `0..(bounds[1] - 1)`, ..., `0..(bounds[Length(bounds) - 1] - 1)`</span></span>

## <a name="input"></a><span data-ttu-id="d7818-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="d7818-108">Input</span></span>

### <a name="bounds--int"></a><span data-ttu-id="d7818-109">sınırlar: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d7818-109">bounds : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="d7818-110">Her Aralık bir tamsayı uzunluğu olarak belirtilmekte olan, tekrarlandırılacak aralıkları belirten bir dizi.</span><span class="sxs-lookup"><span data-stu-id="d7818-110">An array specifying the ranges to be iterated over, with each range being specified as an integer length.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="d7818-111">Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7818-111">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d7818-112">Verilen Kartezyen ürünün her öğesi için çağrılacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="d7818-112">An operation to be called for each element of the given Cartesian product.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7818-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7818-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d7818-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d7818-114">See Also</span></span>

- [<span data-ttu-id="d7818-115">Microsoft. hisse. Canon. IterateThroughCartesianPower</span><span class="sxs-lookup"><span data-stu-id="d7818-115">Microsoft.Quantum.Canon.IterateThroughCartesianPower</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)