---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 77bdb040908e9a8af81dee09451a3582f7b7d159
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733015"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="4b606-102">GreatestCommonDivisorL işlevi</span><span class="sxs-lookup"><span data-stu-id="4b606-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="4b606-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4b606-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4b606-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b606-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b606-105">$A $ ve $b $ öğesinin en büyük ortak bölenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="4b606-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="4b606-106">GCD her zaman pozitif olur.</span><span class="sxs-lookup"><span data-stu-id="4b606-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="4b606-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4b606-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4b606-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b606-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b606-109">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı</span><span class="sxs-lookup"><span data-stu-id="4b606-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4b606-110">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b606-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b606-111">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı</span><span class="sxs-lookup"><span data-stu-id="4b606-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="4b606-112">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4b606-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4b606-113">$a $ ve $b $ öğesinin en büyük ortak böleni</span><span class="sxs-lookup"><span data-stu-id="4b606-113">Greatest common divisor of $a$ and $b$</span></span>