---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814178"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="363b0-102">NormalDistribution işlevi</span><span class="sxs-lookup"><span data-stu-id="363b0-102">NormalDistribution function</span></span>

<span data-ttu-id="363b0-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="363b0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="363b0-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="363b0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="363b0-105">Verilen bir ortalama ve varyans ile normal bir dağıtım döndürür.</span><span class="sxs-lookup"><span data-stu-id="363b0-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="363b0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="363b0-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="363b0-107">Ortalama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="363b0-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="363b0-108">Varyans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="363b0-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="363b0-109">Çıkış: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="363b0-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="363b0-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="363b0-110">Example</span></span>

<span data-ttu-id="363b0-111">Aşağıda, ortalama 2 ve standart sapma 0,1 ile normal dağılıma 10 örnek çizilmiştir:</span><span class="sxs-lookup"><span data-stu-id="363b0-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="363b0-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="363b0-112">See Also</span></span>

- [<span data-ttu-id="363b0-113">Microsoft. hisse. Random. StandardNormalDistribution</span><span class="sxs-lookup"><span data-stu-id="363b0-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)