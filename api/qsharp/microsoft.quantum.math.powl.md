---
uid: Microsoft.Quantum.Math.PowL
title: PowL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: f7282a3639ca87dae731e39594576aa73c4602ac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857460"
---
# <a name="powl-function"></a><span data-ttu-id="860cf-102">PowL işlevi</span><span class="sxs-lookup"><span data-stu-id="860cf-102">PowL function</span></span>

<span data-ttu-id="860cf-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="860cf-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="860cf-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="860cf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="860cf-105">Verilen bir üsle oluşturulan bir sayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="860cf-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="860cf-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="860cf-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="860cf-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="860cf-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="860cf-108">Oluşturulacak $a $ sayısı.</span><span class="sxs-lookup"><span data-stu-id="860cf-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="860cf-109">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="860cf-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="860cf-110">$A $ 'ın üzerinde olması gereken güç $b $.</span><span class="sxs-lookup"><span data-stu-id="860cf-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="860cf-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="860cf-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="860cf-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="860cf-112">The power $a^b$</span></span>