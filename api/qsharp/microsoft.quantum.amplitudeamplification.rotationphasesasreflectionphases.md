---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: Rotationphasesasreflectionaşamalar işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: d62a7584324c9467ccc759e4bed81acbceee719c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731935"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="3a8e0-102">Rotationphasesasreflectionaşamalar işlevi</span><span class="sxs-lookup"><span data-stu-id="3a8e0-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="3a8e0-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="3a8e0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="3a8e0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a8e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a8e0-105">Tek qubit döndürmeler olarak belirtilen aşamaları kısmi yansıtılamalar olarak belirtilen aşamalara dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="3a8e0-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="3a8e0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3a8e0-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="3a8e0-107">Rotaşamaları: [Rotationaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="3a8e0-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="3a8e0-108">Kısmi yansıtımları 'na dönüştürülecek tek qubit döndürmeler dizisi.</span><span class="sxs-lookup"><span data-stu-id="3a8e0-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="3a8e0-109">Çıkış: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="3a8e0-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="3a8e0-110">Kısmi yansıtımları olarak belirtilen aşamaları uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3a8e0-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="3a8e0-111">Referanslar</span><span class="sxs-lookup"><span data-stu-id="3a8e0-111">References</span></span>

<span data-ttu-id="3a8e0-112">İçindeki kuralını kullanıyoruz</span><span class="sxs-lookup"><span data-stu-id="3a8e0-112">We use the convention in</span></span>

- <span data-ttu-id="3a8e0-113">Tek qubit döndürme aşamalarını yansıma işleci aşamalarına ilişkilendirmek için [ *G.H. Low, i. L. Chuang*](https://arxiv.org/abs/1707.05391) .</span><span class="sxs-lookup"><span data-stu-id="3a8e0-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>