---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorL
title: GreatestCommonDivisorL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorL
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 1bd18758bb2dea8a4801cbfdf258d91f81c5d9a4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195536"
---
# <a name="greatestcommondivisorl-function"></a><span data-ttu-id="90395-102">GreatestCommonDivisorL işlevi</span><span class="sxs-lookup"><span data-stu-id="90395-102">GreatestCommonDivisorL function</span></span>

<span data-ttu-id="90395-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90395-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90395-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90395-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90395-105">$A $ ve $b $ öğesinin en büyük ortak bölenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="90395-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="90395-106">GCD her zaman pozitif olur.</span><span class="sxs-lookup"><span data-stu-id="90395-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="90395-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="90395-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="90395-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90395-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90395-109">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı</span><span class="sxs-lookup"><span data-stu-id="90395-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="90395-110">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90395-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90395-111">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı</span><span class="sxs-lookup"><span data-stu-id="90395-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigint"></a><span data-ttu-id="90395-112">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="90395-112">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="90395-113">$a $ ve $b $ öğesinin en büyük ortak böleni</span><span class="sxs-lookup"><span data-stu-id="90395-113">Greatest common divisor of $a$ and $b$</span></span>