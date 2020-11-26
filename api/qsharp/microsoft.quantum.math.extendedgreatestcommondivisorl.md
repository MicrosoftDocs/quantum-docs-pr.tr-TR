---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: abbbd367859952180f181a245ca0754646529b18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210718"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="dcec1-102">ExtendedGreatestCommonDivisorL işlevi</span><span class="sxs-lookup"><span data-stu-id="dcec1-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="dcec1-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="dcec1-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="dcec1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dcec1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dcec1-105">\Cdot a + v \cdot b = \operatorname{GCD} (a, b) $ $u bir demet $ (u, v) $, burada $ \operatorname{GCD} $, $a $ ve $b $ $a $ en büyük ortak bölenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="dcec1-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="dcec1-106">GCD her zaman pozitif olur.</span><span class="sxs-lookup"><span data-stu-id="dcec1-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="dcec1-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="dcec1-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="dcec1-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dcec1-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dcec1-109">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı</span><span class="sxs-lookup"><span data-stu-id="dcec1-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="dcec1-110">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dcec1-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dcec1-111">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı</span><span class="sxs-lookup"><span data-stu-id="dcec1-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="dcec1-112">Çıkış: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="dcec1-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="dcec1-113">Demet $ (u, v) $, özellik $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="dcec1-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="dcec1-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="dcec1-114">References</span></span>

- <span data-ttu-id="dcec1-115">Bu uygulama şunlara göre yapılır https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="dcec1-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>