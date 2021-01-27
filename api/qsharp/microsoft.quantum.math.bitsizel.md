---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848903"
---
# <a name="bitsizel-function"></a><span data-ttu-id="793d8-102">BitSizeL işlevi</span><span class="sxs-lookup"><span data-stu-id="793d8-102">BitSizeL function</span></span>

<span data-ttu-id="793d8-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="793d8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="793d8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="793d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="793d8-105">Negatif olmayan bir tamsayı için `a` , temsil etmesi gereken bitlerin sayısını döndürür `a` .</span><span class="sxs-lookup"><span data-stu-id="793d8-105">For a non-negative integer `a`, returns the number of bits required to represent `a`.</span></span>

<span data-ttu-id="793d8-106">Diğer bir deyişle, $a < 2 ^ n $ gibi en küçük $n $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="793d8-106">That is, returns the smallest $n$ such that $a < 2^n$.</span></span>

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a><span data-ttu-id="793d8-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="793d8-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="793d8-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="793d8-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="793d8-109">Bit boyutu hesaplanacağı tamsayı.</span><span class="sxs-lookup"><span data-stu-id="793d8-109">The integer whose bit-size is to be computed.</span></span>



## <a name="output--int"></a><span data-ttu-id="793d8-110">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="793d8-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="793d8-111">Bit boyutu `a` .</span><span class="sxs-lookup"><span data-stu-id="793d8-111">The bit-size of `a`.</span></span>