---
uid: Microsoft.Quantum.Math.GreatestCommonDivisorI
title: GreatestCommonDivisorI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: GreatestCommonDivisorI
qsharp.summary: Computes the greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 7fd891aa2e4753020ec9ac4e702f8af9edc9df0a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733018"
---
# <a name="greatestcommondivisori-function"></a><span data-ttu-id="847a6-102">GreatestCommonDivisorI işlevi</span><span class="sxs-lookup"><span data-stu-id="847a6-102">GreatestCommonDivisorI function</span></span>

<span data-ttu-id="847a6-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="847a6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="847a6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="847a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="847a6-105">$A $ ve $b $ öğesinin en büyük ortak bölenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="847a6-105">Computes the greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="847a6-106">GCD her zaman pozitif olur.</span><span class="sxs-lookup"><span data-stu-id="847a6-106">The GCD is always positive.</span></span>

```qsharp
function GreatestCommonDivisorI (a : Int, b : Int) : Int
```


## <a name="input"></a><span data-ttu-id="847a6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="847a6-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="847a6-108">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="847a6-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="847a6-109">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı</span><span class="sxs-lookup"><span data-stu-id="847a6-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="847a6-110">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="847a6-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="847a6-111">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı</span><span class="sxs-lookup"><span data-stu-id="847a6-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--int"></a><span data-ttu-id="847a6-112">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="847a6-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="847a6-113">$a $ ve $b $ öğesinin en büyük ortak böleni</span><span class="sxs-lookup"><span data-stu-id="847a6-113">Greatest common divisor of $a$ and $b$</span></span>