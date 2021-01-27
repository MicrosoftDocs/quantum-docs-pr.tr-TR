---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841701"
---
# <a name="applylowdepthand-operation"></a><span data-ttu-id="1b636-102">ApplyLowDepthAnd işlemi</span><span class="sxs-lookup"><span data-stu-id="1b636-102">ApplyLowDepthAnd operation</span></span>

<span data-ttu-id="1b636-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b636-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b636-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b636-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b636-105">Yalnızca her iki denetim qubit de 1 durumda ise, adeklem işlemini gerçekleştirmek için ölçümü kullanarak, belirli bir hedef QUI 'yi tersine çevirir.</span><span class="sxs-lookup"><span data-stu-id="1b636-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1b636-106">Description</span><span class="sxs-lookup"><span data-stu-id="1b636-106">Description</span></span>

<span data-ttu-id="1b636-107">`target`Ve yalnızca her iki denetim 1 ise, ancak 0 durumunda olduğunu varsaymaktadır `target` .</span><span class="sxs-lookup"><span data-stu-id="1b636-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="1b636-108">İşlem T-Count 4, T-Depth 1 ve bir yardımcı qubit gerektirir ve bu nedenle, 0 olarak bilindiğinde CCNOT işlemi tercih edilebilir `target` .</span><span class="sxs-lookup"><span data-stu-id="1b636-108">The operation has T-count 4, T-depth 1 and requires one helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="1b636-109">Bu işlemin adekçine ölçüm tabanlıdır ve hiçbir T kapısı gerektirmez ve yardımcı qubit yoktur.</span><span class="sxs-lookup"><span data-stu-id="1b636-109">The adjoint of this operation is measurement based and requires no T gates, and no helper qubit.</span></span>

## <a name="input"></a><span data-ttu-id="1b636-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="1b636-110">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="1b636-111">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1b636-111">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1b636-112">İlk denetim qubit</span><span class="sxs-lookup"><span data-stu-id="1b636-112">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="1b636-113">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1b636-113">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1b636-114">İkinci denetim qubit</span><span class="sxs-lookup"><span data-stu-id="1b636-114">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1b636-115">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1b636-115">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1b636-116">Hedef yardımcı qubit; 0 durumunda olmalıdır</span><span class="sxs-lookup"><span data-stu-id="1b636-116">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="1b636-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b636-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="1b636-118">Başvurular</span><span class="sxs-lookup"><span data-stu-id="1b636-118">References</span></span>

- <span data-ttu-id="1b636-119">Cody Jones: "hata toleranslı Toffoli kapısı için önemli kurulumlarını", fiziksel. Rev. A 87, 022328, 2013 [Arxıv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="1b636-119">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="1b636-120">Peter Selger: "hisse başına T-derinlik bir", fiziksel. Rev. A 87, 042302, 2013 [Arxıv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302</span><span class="sxs-lookup"><span data-stu-id="1b636-120">Peter Selinger: "Quantum circuits of T-depth one", Phys. Rev. A 87, 042302, 2013 [arXiv:1210.0974](https://arxiv.org/abs/1210.0974) doi:10.1103/PhysRevA.87.042302</span></span>