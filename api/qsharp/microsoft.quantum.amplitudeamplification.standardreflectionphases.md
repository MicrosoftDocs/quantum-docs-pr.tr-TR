---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Standardreflectionaşamalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731922"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="b6a9b-102">Standardreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="b6a9b-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="b6a9b-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b6a9b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b6a9b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6a9b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6a9b-105">Standart genliği yükseltme için kısmi yansıma aşamalarını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="b6a9b-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="b6a9b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6a9b-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="b6a9b-107">Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6a9b-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6a9b-108">İçin kısmi yansıma aşamaları oluşturmak üzere genliği yükseltme yinelemesi sayısı.</span><span class="sxs-lookup"><span data-stu-id="b6a9b-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="b6a9b-109">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b6a9b-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b6a9b-110">Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem</span><span class="sxs-lookup"><span data-stu-id="b6a9b-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="b6a9b-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b6a9b-111">Remarks</span></span>

<span data-ttu-id="b6a9b-112">Başlangıç durumuna ilişkin ilk yansıma ve $0 $ olan hedef durum hakkında son yansıma dışında tüm aşamalar $ \pı $ ' tir.</span><span class="sxs-lookup"><span data-stu-id="b6a9b-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>