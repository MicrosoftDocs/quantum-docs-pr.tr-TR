---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209324"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="454c1-102">ApplyLowDepthAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="454c1-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="454c1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="454c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="454c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="454c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="454c1-105">Yalnızca her iki denetim qubit de 1 durumda ise, adeklem işlemini gerçekleştirmek için ölçümü kullanarak, belirli bir hedef QUI 'yi tersine çevirir.</span><span class="sxs-lookup"><span data-stu-id="454c1-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="454c1-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="454c1-106">Description</span></span>

<span data-ttu-id="454c1-107">`target`Ve yalnızca her iki denetim 1 ise, ancak 0 durumunda olduğunu varsaymaktadır `target` .</span><span class="sxs-lookup"><span data-stu-id="454c1-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="454c1-108">İşlem T-Count 4, T-Depth 1 ve bir yardımcı qubit gerektirir ve bu nedenle, 0 olarak bilindiğinde CCNOT işlemi tercih edilebilir `target` .</span><span class="sxs-lookup"><span data-stu-id="454c1-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="454c1-109">Bu işlemin adekçine ölçüm tabanlıdır ve hiçbir T kapısı gerektirmez ve yardımcı qubit yoktur.</span><span class="sxs-lookup"><span data-stu-id="454c1-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="454c1-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="454c1-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="454c1-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="454c1-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="454c1-112">İlk denetim qubit</span><span class="sxs-lookup"><span data-stu-id="454c1-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="454c1-113">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="454c1-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="454c1-114">İkinci denetim qubit</span><span class="sxs-lookup"><span data-stu-id="454c1-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="454c1-115">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="454c1-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="454c1-116">Hedef yardımcı qubit; 0 durumunda olmalıdır</span><span class="sxs-lookup"><span data-stu-id="454c1-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="454c1-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="454c1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="454c1-118">Başvurular</span><span class="sxs-lookup"><span data-stu-id="454c1-118">References</span></span>

- <span data-ttu-id="454c1-119">Cody Jones: "hata toleranslı Toffoli kapısı için önemli kurulumlarını", fiziksel. Rev. A 87, 022328, 2013 [Arxıv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="454c1-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="454c1-120">Peter Selger: "hisse başına T-derinlik bir", fiziksel. Rev. A 87, 042302, 2013 [Arxıv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="454c1-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>