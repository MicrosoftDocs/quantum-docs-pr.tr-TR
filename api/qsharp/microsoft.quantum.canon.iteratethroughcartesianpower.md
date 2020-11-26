---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206485"
---
# <a name="iteratethroughcartesianpower-operation"></a><span data-ttu-id="2cbe9-102">IterateThroughCartesianPower işlemi</span><span class="sxs-lookup"><span data-stu-id="2cbe9-102">IterateThroughCartesianPower operation</span></span>

<span data-ttu-id="2cbe9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2cbe9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2cbe9-105">Bir tamsayı aralığının Kartezyen kuvveti içindeki her dizin için bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-105">Applies an operation for each index in the Cartesian power of an integer range.</span></span>

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a><span data-ttu-id="2cbe9-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2cbe9-106">Description</span></span>

<span data-ttu-id="2cbe9-107">Yinelemeli olarak, aralığın Kartezyen her öğesi için bir işlem uygular `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="2cbe9-107">Iteratively applies an operation for each element of a Cartesian power of the range `0..(bound - 1)`.</span></span>

## <a name="input"></a><span data-ttu-id="2cbe9-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2cbe9-108">Input</span></span>

### <a name="power--int"></a><span data-ttu-id="2cbe9-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2cbe9-110">Aralığın oluşturulması gereken Kartezyen güç `0..(bound - 1)` .</span><span class="sxs-lookup"><span data-stu-id="2cbe9-110">The Cartesian power to which the range `0..(bound - 1)` should be raised.</span></span>


### <a name="bound--int"></a><span data-ttu-id="2cbe9-111">bağlıydı: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-111">bound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2cbe9-112">Aralığın uzunluğu olarak belirtilen, tekrarlandırılmış aralığın bir belirtimi.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-112">A specification of the range to be iterated over, given as the length of the range.</span></span>


### <a name="op--int--unit"></a><span data-ttu-id="2cbe9-113">Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-113">op : [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2cbe9-114">Verilen Kartezyen her öğe için çağrılacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-114">An operation to be called for each element of the given Cartesian power.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cbe9-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cbe9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="2cbe9-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2cbe9-116">See Also</span></span>

- [<span data-ttu-id="2cbe9-117">Microsoft. hisse. Canon. IterateThroughCartesianProduct</span><span class="sxs-lookup"><span data-stu-id="2cbe9-117">Microsoft.Quantum.Canon.IterateThroughCartesianProduct</span></span>](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)