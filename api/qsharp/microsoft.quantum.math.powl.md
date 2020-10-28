---
uid: Microsoft.Quantum.Math.PowL
title: PowL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733647"
---
# <a name="powl-function"></a><span data-ttu-id="7b296-102">PowL işlevi</span><span class="sxs-lookup"><span data-stu-id="7b296-102">PowL function</span></span>

<span data-ttu-id="7b296-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7b296-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7b296-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b296-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b296-105">Verilen bir üsle oluşturulan bir sayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="7b296-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="7b296-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7b296-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7b296-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b296-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b296-108">Oluşturulacak $a $ sayısı.</span><span class="sxs-lookup"><span data-stu-id="7b296-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="7b296-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b296-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b296-110">$A $ 'ın üzerinde olması gereken güç $b $.</span><span class="sxs-lookup"><span data-stu-id="7b296-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="7b296-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b296-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b296-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="7b296-112">The power $a^b$</span></span>