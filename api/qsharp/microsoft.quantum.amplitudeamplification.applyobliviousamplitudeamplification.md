---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732007"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="108fb-102">ApplyObliviousAmplitudeAmplification işlemi</span><span class="sxs-lookup"><span data-stu-id="108fb-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="108fb-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="108fb-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="108fb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="108fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="108fb-105">, Kısmi yansımalar belirterek yükümlülüğü genliği bir şekilde yükseltme.</span><span class="sxs-lookup"><span data-stu-id="108fb-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="108fb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="108fb-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="108fb-107">Aşamalar: [Reflectionaşamalar](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="108fb-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="108fb-108">Kısmi yansıtımları aşamaları</span><span class="sxs-lookup"><span data-stu-id="108fb-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="108fb-109">Startstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="108fb-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="108fb-110">Yardımcı kaydın başlangıç durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="108fb-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="108fb-111">Targetstatereftaction: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="108fb-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="108fb-112">Yardımcı kaydın hedef durumu hakkında yansıma işleci</span><span class="sxs-lookup"><span data-stu-id="108fb-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="108fb-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="108fb-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="108fb-114">Yardımcı ve sistem Yazmaçları üzerinde ortaklaşa çalışan türde Unitary Oracle $O $ `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="108fb-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="108fb-115">auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="108fb-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="108fb-116">Yardımcı kayıt</span><span class="sxs-lookup"><span data-stu-id="108fb-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="108fb-117">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="108fb-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="108fb-118">Sistem kaydı</span><span class="sxs-lookup"><span data-stu-id="108fb-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="108fb-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="108fb-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="108fb-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="108fb-120">Remarks</span></span>

<span data-ttu-id="108fb-121">Belirli bir yardımcı başlangıç durumu $ \ket{\Text{Start}} \_ a $, belirli bir yardımcı hedef durumu $ \ket{\Text{Target}} \_ a $ ve herhangi bir sistem durumu $ \ket{\psı} \_ s $ olarak verildi. \begin{hizalaması} o\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambdad\ket{\Text{Target}} \_ a U \ket{\psıd olduğunu varsayalım.} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cnoktalar \end{hizalaması}, bazı Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="108fb-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="108fb-122">, Ve Adjoint 'ın uygulamaları tarafından, yardımcı kayıt arasındaki başlangıç ve hedef durumları hakkında bir dizi yansıma ile `signalOracle` , U 'nin uygulanması için başarılı olma olasılığı da değişebilir.</span><span class="sxs-lookup"><span data-stu-id="108fb-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="108fb-123">Çoğu durumda, `auxiliaryRegister` $ \ket{\Text{Start}} \_ a $ durumunda başlatılır.</span><span class="sxs-lookup"><span data-stu-id="108fb-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="108fb-124">Referanslar</span><span class="sxs-lookup"><span data-stu-id="108fb-124">References</span></span>

<span data-ttu-id="108fb-125">Bkz.</span><span class="sxs-lookup"><span data-stu-id="108fb-125">See</span></span>

- <span data-ttu-id="108fb-126">Standart sürüm için [ *D.W. Braz, Child, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) .</span><span class="sxs-lookup"><span data-stu-id="108fb-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="108fb-127">Bkz.</span><span class="sxs-lookup"><span data-stu-id="108fb-127">See</span></span>
- <span data-ttu-id="108fb-128">[ *G.H. Low, I.L. Chuang*](https://arxiv.org/abs/1610.06546) kısmi yansıtımları Genelleştirme için.</span><span class="sxs-lookup"><span data-stu-id="108fb-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>