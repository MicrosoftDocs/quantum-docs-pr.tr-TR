---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195537"
---
# <a name="extendedgreatestcommondivisori-function"></a><span data-ttu-id="e2580-102">ExtendedGreatestCommonDivisorI işlevi</span><span class="sxs-lookup"><span data-stu-id="e2580-102">ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="e2580-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e2580-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e2580-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2580-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2580-105">\Cdot a + v \cdot b = \operatorname{GCD} (a, b) $ $u bir demet $ (u, v) $, burada $ \operatorname{GCD} $, $a $ ve $b $ $a $ en büyük ortak bölenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="e2580-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="e2580-106">GCD her zaman pozitif olur.</span><span class="sxs-lookup"><span data-stu-id="e2580-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="e2580-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e2580-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="e2580-108">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2580-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2580-109">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ilk sayı</span><span class="sxs-lookup"><span data-stu-id="e2580-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--int"></a><span data-ttu-id="e2580-110">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2580-110">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2580-111">Genişletilmiş en büyük ortak ayırıcının hesaplandığı ikinci sayı</span><span class="sxs-lookup"><span data-stu-id="e2580-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--intint"></a><span data-ttu-id="e2580-112">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="e2580-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="e2580-113">Demet $ (u, v) $, özellik $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $.</span><span class="sxs-lookup"><span data-stu-id="e2580-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="e2580-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="e2580-114">References</span></span>

- <span data-ttu-id="e2580-115">Bu uygulama şunlara göre yapılır https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="e2580-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>