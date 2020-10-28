---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotationaşamalar Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731943"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="ef3e2-102">Rotationaşamalar Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="ef3e2-102">RotationPhases user defined type</span></span>

<span data-ttu-id="ef3e2-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="ef3e2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="ef3e2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ef3e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ef3e2-105">Tek qubit döndürmeler dizisinin bir sırası için aşamalar yükseltme.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="ef3e2-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ef3e2-106">Remarks</span></span>

<span data-ttu-id="ef3e2-107">İlk parametre, tek qubit döndürmelerdeki bir ürün olarak ifade edilen, yansımalar için bir dizi aşamadan oluşur.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="ef3e2-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-108">[ G.H.</span></span> <span data-ttu-id="ef3e2-109">Düşük, ı. L.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-109">Low, I. L.</span></span> <span data-ttu-id="ef3e2-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="ef3e2-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>