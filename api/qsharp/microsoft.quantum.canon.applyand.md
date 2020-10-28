---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Applyve işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729743"
---
# <a name="applyand-operation"></a><span data-ttu-id="94b16-102">Applyve işlemi</span><span class="sxs-lookup"><span data-stu-id="94b16-102">ApplyAnd operation</span></span>

<span data-ttu-id="94b16-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94b16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94b16-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94b16-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94b16-105">Yalnızca her iki denetim qubit de 1 durumundaysa, adjoint işlemini gerçekleştirmek için ölçüm kullanarak, belirli bir hedef qubit 'i tersine çevirir.</span><span class="sxs-lookup"><span data-stu-id="94b16-105">Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.</span></span>

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="94b16-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="94b16-106">Description</span></span>

<span data-ttu-id="94b16-107">`target`Ve yalnızca her iki denetim 1 ise, ancak 0 durumunda olduğunu varsaymaktadır `target` .</span><span class="sxs-lookup"><span data-stu-id="94b16-107">Inverts `target` if and only if both controls are 1, but assumes that `target` is in state 0.</span></span>  <span data-ttu-id="94b16-108">İşlem T-Count 4, T-Depth 2 ' dir ve yardımcı qubit gerektirmez ve bu nedenle, 0 olarak bilindiğinde CCNOT işlemi tercih edilebilir `target` .</span><span class="sxs-lookup"><span data-stu-id="94b16-108">The operation has T-count 4, T-depth 2 and requires no helper qubit, and may therefore be preferable to a CCNOT operation, if `target` is known to be 0.</span></span>  <span data-ttu-id="94b16-109">Bu işlemin adekçi, ölçüm tabanlıdır ve T kapısı gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="94b16-109">The adjoint of this operation is measurement based and requires no T gates.</span></span>

<span data-ttu-id="94b16-110">Bu işlemin denetlenen uygulaması, hiçbir yardımcı qubit, kapı gerektirmez `2^c` `Rz` ve bu işlem için en iyi duruma getirilmemiştir; burada `c` işlemin iki denetimi de dahil olmak üzere genel denetim qugeler sayısıdır `ApplyAnd` .</span><span class="sxs-lookup"><span data-stu-id="94b16-110">The controlled application of this operation requires no helper qubit, `2^c` `Rz` gates and is not optimized for depth, where `c` is the number of overall control qubits including the two controls from the `ApplyAnd` operation.</span></span>  <span data-ttu-id="94b16-111">Adjoint kontrollü uygulama, `2^c - 1` `Rz` kapıları (adjoint olmayan işlemin boyutunun iki katı kadar bir açıda), yardımcı qubit olmadan ve derinlemesine en iyi duruma getirilmemelidir.</span><span class="sxs-lookup"><span data-stu-id="94b16-111">The adjoint controlled application requires `2^c - 1` `Rz` gates (with an angle twice the size of the non-adjoint operation), no helper qubit and is not optimized for depth.</span></span>

## <a name="input"></a><span data-ttu-id="94b16-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="94b16-112">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="94b16-113">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94b16-113">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94b16-114">İlk denetim qubit</span><span class="sxs-lookup"><span data-stu-id="94b16-114">First control qubit</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="94b16-115">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94b16-115">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94b16-116">İkinci denetim qubit</span><span class="sxs-lookup"><span data-stu-id="94b16-116">Second control qubit</span></span>


### <a name="target--qubit"></a><span data-ttu-id="94b16-117">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="94b16-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="94b16-118">Hedef yardımcı qubit; 0 durumunda olmalıdır</span><span class="sxs-lookup"><span data-stu-id="94b16-118">Target auxiliary qubit; must be in state 0</span></span>



## <a name="output--unit"></a><span data-ttu-id="94b16-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94b16-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="94b16-120">Referanslar</span><span class="sxs-lookup"><span data-stu-id="94b16-120">References</span></span>

- <span data-ttu-id="94b16-121">Cody Jones: "hata toleranslı Toffoli kapısı için önemli kurulumlarını", fiziksel. Rev. A 87, 022328, 2013 [Arxıv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328</span><span class="sxs-lookup"><span data-stu-id="94b16-121">Cody Jones: "Novel constructions for the fault-tolerant Toffoli gate", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328</span></span>
- <span data-ttu-id="94b16-122">Craig Gidney: "hisse alma maliyetini durdurma", hisse 2, sayfa 74, 2018 [Arxıv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302</span><span class="sxs-lookup"><span data-stu-id="94b16-122">Craig Gidney: "Halving the cost of quantum addition", Quantum 2, page 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302</span></span>
- <span data-ttu-id="94b16-123">Mathias Soeken: "hisse senedi Oracle devreleri ve Noel ağacı", [Blog makalesi 19 aralık 2019](https://msoeken.github.io/blog_qac.html) (Note: birden çok kontrollü oluşturma açıklanır)</span><span class="sxs-lookup"><span data-stu-id="94b16-123">Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree Pattern", [Blog article from December 19, 2019](https://msoeken.github.io/blog_qac.html) (note: explains the multiple controlled construction)</span></span>