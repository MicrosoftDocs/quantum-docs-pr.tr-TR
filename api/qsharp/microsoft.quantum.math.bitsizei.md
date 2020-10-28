---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732759"
---
# <a name="bitsizei-function"></a><span data-ttu-id="396b6-102">BitSizeI işlevi</span><span class="sxs-lookup"><span data-stu-id="396b6-102">BitSizeI function</span></span>

<span data-ttu-id="396b6-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="396b6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="396b6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="396b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="396b6-105">Negatif olmayan bir tamsayı için `a` , temsil etmesi gereken bitlerin sayısını döndürür `a` .</span><span class="sxs-lookup"><span data-stu-id="396b6-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="396b6-106">Diğer bir deyişle, $a < 2 ^ n $ gibi en küçük $n $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="396b6-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="396b6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="396b6-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="396b6-108">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="396b6-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="396b6-109">Bit boyutu hesaplanacağı tamsayı.</span><span class="sxs-lookup"><span data-stu-id="396b6-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="396b6-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="396b6-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="396b6-111">Bit boyutu `a` .</span><span class="sxs-lookup"><span data-stu-id="396b6-111">The bit-size of `a`.</span></span>