---
uid: Microsoft.Quantum.Math.PowL
title: PowL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: b3207d1854f6b69cdb5b68d354000a0b6746c0c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228330"
---
# <a name="powl-function"></a><span data-ttu-id="7b57f-102">PowL işlevi</span><span class="sxs-lookup"><span data-stu-id="7b57f-102">PowL function</span></span>

<span data-ttu-id="7b57f-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7b57f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7b57f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b57f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b57f-105">Verilen bir üsle oluşturulan bir sayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="7b57f-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="7b57f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7b57f-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="7b57f-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b57f-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b57f-108">Oluşturulacak $a $ sayısı.</span><span class="sxs-lookup"><span data-stu-id="7b57f-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="7b57f-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b57f-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7b57f-110">$A $ 'ın üzerinde olması gereken güç $b $.</span><span class="sxs-lookup"><span data-stu-id="7b57f-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="7b57f-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7b57f-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7b57f-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="7b57f-112">The power $a^b$</span></span>