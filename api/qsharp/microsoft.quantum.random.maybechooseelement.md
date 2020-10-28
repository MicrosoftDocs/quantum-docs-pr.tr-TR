---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732170"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="ca6d6-102">MaybeChooseElement işlemi</span><span class="sxs-lookup"><span data-stu-id="ca6d6-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="ca6d6-103">Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ca6d6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ca6d6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca6d6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca6d6-105">Veri dizisi ve dizinleri üzerinde bir dağıtım verildiğinde, rastgele bir öğe seçme girişiminde bulunur.</span><span class="sxs-lookup"><span data-stu-id="ca6d6-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="ca6d6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ca6d6-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="ca6d6-107">veri: 'T []</span><span class="sxs-lookup"><span data-stu-id="ca6d6-107">data : 'T[]</span></span>

<span data-ttu-id="ca6d6-108">Bir öğenin seçilmesi gereken dizi.</span><span class="sxs-lookup"><span data-stu-id="ca6d6-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="ca6d6-109">ındexdistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="ca6d6-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="ca6d6-110">Dizinleri üzerinden bir dağıtım `data` .</span><span class="sxs-lookup"><span data-stu-id="ca6d6-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="ca6d6-111">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="ca6d6-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca6d6-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ca6d6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca6d6-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ca6d6-113">'T</span></span>

