---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontroltadonınt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845109"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="bf321-102">Applycontroltadonınt işlemi</span><span class="sxs-lookup"><span data-stu-id="bf321-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="bf321-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bf321-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bf321-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bf321-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bf321-105">Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="bf321-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bf321-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bf321-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="bf321-107">numberState: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf321-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf321-108">İşlemin denetlenmesi gereken negatif olmayan bir tamsayı `oracle` .</span><span class="sxs-lookup"><span data-stu-id="bf321-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="bf321-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL</span><span class="sxs-lookup"><span data-stu-id="bf321-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bf321-110">Denetimli bir Unitary işlemi.</span><span class="sxs-lookup"><span data-stu-id="bf321-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="bf321-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bf321-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bf321-112">Uygulamasını denetleyen bir hisse kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="bf321-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="bf321-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="bf321-113">targetRegister : 'T</span></span>

<span data-ttu-id="bf321-114">Uygulanacağı kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="bf321-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf321-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf321-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bf321-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bf321-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bf321-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bf321-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bf321-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="bf321-118">Remarks</span></span>

<span data-ttu-id="bf321-119">Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="bf321-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="bf321-120">`numberState` en fazla $2 ^ \texttt{Length (controlRegister)}-$1 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="bf321-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="bf321-121">Örneğin, `numberState = 537` `oracle` yalnızca `controlRegister` $ \ket $ durumunda ise uygulandığı anlamına gelir {537} .</span><span class="sxs-lookup"><span data-stu-id="bf321-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>