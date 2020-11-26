---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontroltadonbitstring işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 6947d2dbdec4cfbb592143024a7c8ccd53a32029
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219082"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="73594-102">Applycontroltadonbitstring işlemi</span><span class="sxs-lookup"><span data-stu-id="73594-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="73594-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="73594-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="73594-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73594-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73594-105">Hedef kayıt üzerinde, belirli bir bit maskesi tarafından belirtilen bir duruma göre denetlenen bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="73594-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="73594-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="73594-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="73594-107">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="73594-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="73594-108">Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.</span><span class="sxs-lookup"><span data-stu-id="73594-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="73594-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="73594-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="73594-110">Hedef kaydına uygulanacak Unitary işlemi.</span><span class="sxs-lookup"><span data-stu-id="73594-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="73594-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="73594-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="73594-112">Uygulamasını denetleyen bir hisse kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="73594-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="73594-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="73594-113">targetRegister : 'T</span></span>

<span data-ttu-id="73594-114">Giriş olarak geçirilecek hedef kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="73594-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="73594-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="73594-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="73594-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="73594-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="73594-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="73594-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="73594-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="73594-118">Remarks</span></span>

<span data-ttu-id="73594-119">Tarafından verilen model `bits` öğesinden daha kısa olabilir `controlRegister` , bu durumda ek denetim qugeler yok sayılır (yani, $ \grex {0} veya $ \ket $ üzerinde denetlenmez {1} ).</span><span class="sxs-lookup"><span data-stu-id="73594-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="73594-120">`bits`Daha uzunsa `controlRegister` bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="73594-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="73594-121">Örneğin, `bits = [0,1,0,0,1]` `oracle` ancak yalnızca `controlRegister` $ \ ayraç {0} \ ayraç {1} {0} {0} \ ayraç {1} \ ayraç \ kutusunda ise geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="73594-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>