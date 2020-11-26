---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203239"
---
# <a name="decomposedon-function"></a><span data-ttu-id="0231f-102">DecomposedOn işlevi</span><span class="sxs-lookup"><span data-stu-id="0231f-102">DecomposedOn function</span></span>

<span data-ttu-id="0231f-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0231f-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0231f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0231f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0231f-105">Bir değişken üzerinde bir permütasyon 'yi kaldırır</span><span class="sxs-lookup"><span data-stu-id="0231f-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="0231f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0231f-106">Description</span></span>

<span data-ttu-id="0231f-107">Bir permütasyon $ \pı $ ( `perm` ) ve bir dizin $i $ () verildiğinde `index` , bu yöntem, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bit değiştirmelerini sağlayan üç permütasyon $ ((\ pi_l, \ pi_r), \pı ') $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="0231f-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="0231f-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="0231f-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="0231f-109">izin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0231f-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="0231f-110">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0231f-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="0231f-111">Çıkış: (([Int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="0231f-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

