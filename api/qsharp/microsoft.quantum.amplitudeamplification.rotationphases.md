---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotationaşamalar Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 60fcda7d58a19f8891e252ddb18b504afddf5514
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191372"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="6f566-102">Rotationaşamalar Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="6f566-102">RotationPhases user defined type</span></span>

<span data-ttu-id="6f566-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="6f566-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="6f566-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f566-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f566-105">Tek qubit döndürmeler dizisinin bir sırası için aşamalar yükseltme.</span><span class="sxs-lookup"><span data-stu-id="6f566-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="6f566-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6f566-106">Remarks</span></span>

<span data-ttu-id="6f566-107">İlk parametre, tek qubit döndürmelerdeki bir ürün olarak ifade edilen, yansımalar için bir dizi aşamadan oluşur.</span><span class="sxs-lookup"><span data-stu-id="6f566-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="6f566-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="6f566-108">[ G.H.</span></span> <span data-ttu-id="6f566-109">Düşük, ı. L.</span><span class="sxs-lookup"><span data-stu-id="6f566-109">Low, I. L.</span></span> <span data-ttu-id="6f566-110">Chuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="6f566-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>