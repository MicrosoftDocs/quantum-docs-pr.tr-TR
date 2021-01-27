---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Fixedpointreflectionaşamalar işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 2ded197801111c26d8a33f9c2363b46ca4b6c4b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845851"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="344e3-102">Fixedpointreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="344e3-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="344e3-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="344e3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="344e3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="344e3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="344e3-105">Sabit nokta genliği yükseltme için kısmi yansıma aşamalarını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="344e3-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="344e3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="344e3-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="344e3-107">nQueries: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="344e3-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="344e3-108">Durum hazırlığı Oracle 'a yapılan sorgu sayısı.</span><span class="sxs-lookup"><span data-stu-id="344e3-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="344e3-109">Tek bir tamsayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="344e3-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="344e3-110">Başarılı smın: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="344e3-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="344e3-111">Hedef en kısa başarı olasılığı.</span><span class="sxs-lookup"><span data-stu-id="344e3-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="344e3-112">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="344e3-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="344e3-113">Sabit nokta genampme hisse algoritması uygulamasında kullanılabilen aşamaların dizisi.</span><span class="sxs-lookup"><span data-stu-id="344e3-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="344e3-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="344e3-114">References</span></span>

<span data-ttu-id="344e3-115">"En Iyi sayıdaki sorgu ile sabit noktalı geniz yükseltme" aşamalarını kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="344e3-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="344e3-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Ayrıca bkz. "bileşik hisse kapıları Metodolojisi"</span><span class="sxs-lookup"><span data-stu-id="344e3-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="344e3-117">[](https://arxiv.org/abs/1603.03996) Şu biçimdeki aşamalar için LowYoderChuang2016 `RotationPhases` .</span><span class="sxs-lookup"><span data-stu-id="344e3-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>