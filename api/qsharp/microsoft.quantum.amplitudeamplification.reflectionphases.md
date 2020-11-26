---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Reflectionaşamalar Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191355"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="70cd0-102">Reflectionaşamalar Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="70cd0-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="70cd0-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="70cd0-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="70cd0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70cd0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70cd0-105">Genize göre kısmi yansıtımları dizisinin aşamaları.</span><span class="sxs-lookup"><span data-stu-id="70cd0-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="70cd0-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="70cd0-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="70cd0-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="70cd0-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="70cd0-108">Başlangıç durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="70cd0-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="70cd0-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="70cd0-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="70cd0-110">Hedef durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="70cd0-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="70cd0-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="70cd0-111">Remarks</span></span>

<span data-ttu-id="70cd0-112">Her iki dizi de aynı uzunlukta olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="70cd0-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="70cd0-113">Çoğu durumda, hedef durum hakkında başlangıç durumu ve son aşama hakkında ilk aşamanın genel bir aşama kaydırma ve $0 $ olarak ayarlanması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="70cd0-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>