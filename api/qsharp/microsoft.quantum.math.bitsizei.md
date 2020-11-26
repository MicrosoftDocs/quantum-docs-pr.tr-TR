---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195860"
---
# <a name="bitsizei-function"></a><span data-ttu-id="e581b-102">BitSizeI işlevi</span><span class="sxs-lookup"><span data-stu-id="e581b-102">BitSizeI function</span></span>

<span data-ttu-id="e581b-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e581b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e581b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e581b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e581b-105">Negatif olmayan bir tamsayı için `a` , temsil etmesi gereken bitlerin sayısını döndürür `a` .</span><span class="sxs-lookup"><span data-stu-id="e581b-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="e581b-106">Diğer bir deyişle, $a < 2 ^ n $ gibi en küçük $n $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="e581b-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="e581b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e581b-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e581b-108">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e581b-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e581b-109">Bit boyutu hesaplanacağı tamsayı.</span><span class="sxs-lookup"><span data-stu-id="e581b-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="e581b-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e581b-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e581b-111">Bit boyutu `a` .</span><span class="sxs-lookup"><span data-stu-id="e581b-111">The bit-size of `a`.</span></span>