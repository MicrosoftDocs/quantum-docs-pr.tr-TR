---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840289"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="57cdd-102">IterateThroughCartesianPower işlemi</span><span class="sxs-lookup"><span data-stu-id="57cdd-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="57cdd-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="57cdd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="57cdd-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57cdd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57cdd-105">Bir tamsayı aralığının Kartezyen kuvveti içindeki her dizin için bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="57cdd-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="57cdd-106">Description</span><span class="sxs-lookup"><span data-stu-id="57cdd-106">Description</span></span>

<span data-ttu-id="57cdd-107">Yinelemeli olarak, aralığın Kartezyen her öğesi için bir işlem uygular `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="57cdd-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="57cdd-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="57cdd-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="57cdd-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57cdd-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57cdd-110">Aralığın oluşturulması gereken Kartezyen güç `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="57cdd-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="57cdd-111">bağlıydı: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57cdd-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57cdd-112">Aralığın uzunluğu olarak belirtilen, tekrarlandırılmış aralığın bir belirtimi.</span><span class="sxs-lookup"><span data-stu-id="57cdd-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="57cdd-113">Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57cdd-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="57cdd-114">Verilen Kartezyen her öğe için çağrılacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="57cdd-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="57cdd-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="57cdd-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="57cdd-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="57cdd-116">Example</span></span>

<span data-ttu-id="57cdd-117">Bir işlem verildiğinde `op` , aşağıdaki iki kod parçacığı eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="57cdd-117">Given an operation `op`, the following two snippets are equivalent:</span></span>

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a><span data-ttu-id="57cdd-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="57cdd-118">See Also</span></span>

- [<span data-ttu-id="57cdd-119">Microsoft. hisse. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="57cdd-119">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)