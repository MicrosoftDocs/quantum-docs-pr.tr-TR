---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: Standardreflectionaşamalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843909"
---
# <a name="standardreflectionphases-function"></a><span data-ttu-id="c4116-102">Standardreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="c4116-102">StandardReflectionPhases function</span></span>

<span data-ttu-id="c4116-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c4116-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c4116-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4116-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4116-105">Standart genliği yükseltme için kısmi yansıma aşamalarını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="c4116-105">Computes partial reflection phases for standard amplitude amplification.</span></span>

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="c4116-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c4116-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="c4116-107">Nyinelemeler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c4116-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c4116-108">İçin kısmi yansıma aşamaları oluşturmak üzere genliği yükseltme yinelemesi sayısı.</span><span class="sxs-lookup"><span data-stu-id="c4116-108">Number of amplitude amplification iterations to generate partial reflection phases for.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="c4116-109">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="c4116-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="c4116-110">Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem</span><span class="sxs-lookup"><span data-stu-id="c4116-110">An operation that implements phases specified as partial reflections</span></span>

## <a name="remarks"></a><span data-ttu-id="c4116-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c4116-111">Remarks</span></span>

<span data-ttu-id="c4116-112">Başlangıç durumuna ilişkin ilk yansıma ve $0 $ olan hedef durum hakkında son yansıma dışında tüm aşamalar $ \pı $ ' tir.</span><span class="sxs-lookup"><span data-stu-id="c4116-112">All phases are $\pi$, except for the first reflection about the start state and the last reflection about the target state, which are $0$.</span></span>