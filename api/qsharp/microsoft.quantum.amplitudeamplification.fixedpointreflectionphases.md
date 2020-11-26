---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: Fixedpointreflectionaşamalar işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191458"
---
# <a name="fixedpointreflectionphases-function"></a><span data-ttu-id="b4ba8-102">Fixedpointreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="b4ba8-102">FixedPointReflectionPhases function</span></span>

<span data-ttu-id="b4ba8-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b4ba8-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b4ba8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b4ba8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b4ba8-105">Sabit nokta genliği yükseltme için kısmi yansıma aşamalarını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="b4ba8-105">Computes partial reflection phases for fixed-point amplitude amplification.</span></span>

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="b4ba8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b4ba8-106">Input</span></span>

### <a name="nqueries--int"></a><span data-ttu-id="b4ba8-107">nQueries: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4ba8-107">nQueries : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4ba8-108">Durum hazırlığı Oracle 'a yapılan sorgu sayısı.</span><span class="sxs-lookup"><span data-stu-id="b4ba8-108">Number of queries to the state preparation oracle.</span></span> <span data-ttu-id="b4ba8-109">Tek bir tamsayı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b4ba8-109">Must be an odd integer.</span></span>


### <a name="successmin--double"></a><span data-ttu-id="b4ba8-110">Başarılı smın: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b4ba8-110">successMin : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b4ba8-111">Hedef en kısa başarı olasılığı.</span><span class="sxs-lookup"><span data-stu-id="b4ba8-111">Target minimum success probability.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="b4ba8-112">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="b4ba8-112">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="b4ba8-113">Sabit nokta genampme hisse algoritması uygulamasında kullanılabilen aşamaların dizisi.</span><span class="sxs-lookup"><span data-stu-id="b4ba8-113">Array of phases that can be used in fixed-point amplitude amplification quantum algorithm implementation.</span></span>

## <a name="references"></a><span data-ttu-id="b4ba8-114">Başvurular</span><span class="sxs-lookup"><span data-stu-id="b4ba8-114">References</span></span>

<span data-ttu-id="b4ba8-115">"En Iyi sayıdaki sorgu ile sabit noktalı geniz yükseltme" aşamalarını kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="b4ba8-115">We use the phases in "Fixed-Point Amplitude Amplification with an Optimal Number of Queries"</span></span>

- <span data-ttu-id="b4ba8-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) Ayrıca bkz. "bileşik hisse kapıları Metodolojisi"</span><span class="sxs-lookup"><span data-stu-id="b4ba8-116">[YoderLowChuang2014](https://arxiv.org/abs/1409.3305) See also "Methodology of composite quantum gates"</span></span>
- <span data-ttu-id="b4ba8-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) Şu biçimdeki aşamalar için LowYoderChuang2016 `RotationPhases` .</span><span class="sxs-lookup"><span data-stu-id="b4ba8-117">[LowYoderChuang2016](https://arxiv.org/abs/1603.03996) for phases in the `RotationPhases` format.</span></span>