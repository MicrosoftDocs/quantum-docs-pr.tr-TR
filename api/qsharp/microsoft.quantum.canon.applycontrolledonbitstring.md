---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontroltadonbitstring işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841940"
---
# <a name="applycontrolledonbitstring-operation"></a><span data-ttu-id="94de2-102">Applycontroltadonbitstring işlemi</span><span class="sxs-lookup"><span data-stu-id="94de2-102">ApplyControlledOnBitString operation</span></span>

<span data-ttu-id="94de2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94de2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94de2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94de2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94de2-105">Hedef kayıt üzerinde, belirli bir bit maskesi tarafından belirtilen bir duruma göre denetlenen bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="94de2-105">Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.</span></span>

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="94de2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="94de2-106">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="94de2-107">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="94de2-107">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="94de2-108">Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.</span><span class="sxs-lookup"><span data-stu-id="94de2-108">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="94de2-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="94de2-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="94de2-110">Hedef kaydına uygulanacak Unitary işlemi.</span><span class="sxs-lookup"><span data-stu-id="94de2-110">The unitary operation to be applied on the target register.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="94de2-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94de2-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94de2-112">Uygulamasını denetleyen bir hisse kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="94de2-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="94de2-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="94de2-113">targetRegister : 'T</span></span>

<span data-ttu-id="94de2-114">Giriş olarak geçirilecek hedef kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="94de2-114">The target register to be passed to `oracle` as an input.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94de2-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94de2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94de2-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="94de2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94de2-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="94de2-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="94de2-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="94de2-118">Remarks</span></span>

<span data-ttu-id="94de2-119">Tarafından verilen model `bits` öğesinden daha kısa olabilir `controlRegister` , bu durumda ek denetim qugeler yok sayılır (yani, $ \grex {0} veya $ \ket $ üzerinde denetlenmez {1} ).</span><span class="sxs-lookup"><span data-stu-id="94de2-119">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="94de2-120">`bits`Daha uzunsa `controlRegister` bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="94de2-120">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="94de2-121">Örneğin, `bits = [0,1,0,0,1]` `oracle` ancak yalnızca `controlRegister` $ \ ayraç {0} \ ayraç {1} {0} {0} \ ayraç {1} \ ayraç \ kutusunda ise geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="94de2-121">For example, `bits = [0,1,0,0,1]` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{0}\ket{1}\ket{0}\ket{0}\ket{1}$.</span></span>