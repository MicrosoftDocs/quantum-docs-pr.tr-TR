---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontroltadonınt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729671"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="2f566-102">Applycontroltadonınt işlemi</span><span class="sxs-lookup"><span data-stu-id="2f566-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="2f566-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f566-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f566-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f566-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2f566-105">Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="2f566-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="2f566-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2f566-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="2f566-107">numberState: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f566-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f566-108">İşlemin denetlenmesi gereken negatif olmayan bir tamsayı `oracle` .</span><span class="sxs-lookup"><span data-stu-id="2f566-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="2f566-109">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="2f566-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2f566-110">Denetimli bir Unitary işlemi.</span><span class="sxs-lookup"><span data-stu-id="2f566-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="2f566-111">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2f566-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2f566-112">Uygulamasını denetleyen bir hisse kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="2f566-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="2f566-113">targetRegister: 'T</span><span class="sxs-lookup"><span data-stu-id="2f566-113">targetRegister : 'T</span></span>

<span data-ttu-id="2f566-114">Uygulanacağı kayıt `oracle` .</span><span class="sxs-lookup"><span data-stu-id="2f566-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f566-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f566-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2f566-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2f566-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f566-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2f566-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2f566-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2f566-118">Remarks</span></span>

<span data-ttu-id="2f566-119">Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.</span><span class="sxs-lookup"><span data-stu-id="2f566-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="2f566-120">`numberState` en fazla $2 ^ \texttt{Length (controlRegister)}-$1 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="2f566-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="2f566-121">Örneğin, `numberState = 537` `oracle` yalnızca `controlRegister` $ \ket $ durumunda ise uygulandığı anlamına gelir {537} .</span><span class="sxs-lookup"><span data-stu-id="2f566-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>