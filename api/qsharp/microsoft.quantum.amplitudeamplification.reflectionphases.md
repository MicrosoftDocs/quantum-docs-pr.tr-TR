---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Reflectionaşamalar Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847172"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="03444-102">Reflectionaşamalar Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="03444-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="03444-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="03444-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="03444-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03444-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03444-105">Genize göre kısmi yansıtımları dizisinin aşamaları.</span><span class="sxs-lookup"><span data-stu-id="03444-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="03444-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="03444-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="03444-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="03444-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="03444-108">Başlangıç durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="03444-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="03444-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="03444-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="03444-110">Hedef durumu hakkında yansıma için bir aşamalar dizisi.</span><span class="sxs-lookup"><span data-stu-id="03444-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="03444-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="03444-111">Remarks</span></span>

<span data-ttu-id="03444-112">Her iki dizi de aynı uzunlukta olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="03444-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="03444-113">Çoğu durumda, hedef durum hakkında başlangıç durumu ve son aşama hakkında ilk aşamanın genel bir aşama kaydırma ve $0 $ olarak ayarlanması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="03444-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>