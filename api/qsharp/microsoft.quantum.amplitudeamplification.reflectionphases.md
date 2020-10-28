---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Reflectionaşamalar Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731970"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="bc0a7-102">Reflectionaşamalar Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="bc0a7-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="bc0a7-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bc0a7-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bc0a7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc0a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc0a7-105">Genize göre kısmi yansıtımları dizisinin aşamaları.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="bc0a7-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="bc0a7-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="bc0a7-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bc0a7-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bc0a7-108">Başlangıç durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="bc0a7-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bc0a7-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bc0a7-110">Hedef durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc0a7-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bc0a7-111">Remarks</span></span>

<span data-ttu-id="bc0a7-112">Her iki dizi de aynı uzunlukta olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="bc0a7-113">Çoğu durumda, hedef durum hakkında başlangıç durumu ve son aşama hakkında ilk aşamanın genel bir aşama kaydırma ve $0 $ olarak ayarlanması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>