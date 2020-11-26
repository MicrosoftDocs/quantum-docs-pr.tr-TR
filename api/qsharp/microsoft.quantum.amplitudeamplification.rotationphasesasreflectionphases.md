---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Rotationphasesasreflectionaşamalar işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191202"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="1b650-102">Rotationphasesasreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="1b650-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="1b650-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1b650-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1b650-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b650-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b650-105">Tek qubit döndürmeler olarak belirtilen aşamaları kısmi yansıtılamalar olarak belirtilen aşamalara dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="1b650-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="1b650-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1b650-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="1b650-107">Rotaşamaları: [Rotationaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="1b650-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="1b650-108">Kısmi yansıtımları 'na dönüştürülecek tek qubit döndürmeler dizisi.</span><span class="sxs-lookup"><span data-stu-id="1b650-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="1b650-109">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="1b650-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="1b650-110">Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="1b650-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="1b650-111">Başvurular</span><span class="sxs-lookup"><span data-stu-id="1b650-111">References</span></span>

<span data-ttu-id="1b650-112">İçindeki kuralını kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="1b650-112">We use the convention in</span></span>

- <span data-ttu-id="1b650-113">Tek qubit döndürme aşamalarını yansıma işleci aşamalarına ilişkilendirmek için [ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) .</span><span class="sxs-lookup"><span data-stu-id="1b650-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>