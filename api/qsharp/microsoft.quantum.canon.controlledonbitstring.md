---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Controltadonbitstring işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: ca5a6e116eff187060f7a160e42836b170f0362d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728819"
---
# <a name="controlledonbitstring-function"></a><span data-ttu-id="865cb-102">Controltadonbitstring işlevi</span><span class="sxs-lookup"><span data-stu-id="865cb-102">ControlledOnBitString function</span></span>

<span data-ttu-id="865cb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="865cb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="865cb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="865cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="865cb-105">Denetim yazmacı durumu belirtilen bir bit maskesine karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan Unitary işlemini döndürür.</span><span class="sxs-lookup"><span data-stu-id="865cb-105">Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.</span></span>

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="865cb-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="865cb-106">Description</span></span>

<span data-ttu-id="865cb-107">Bu işlevin çıktısı, bir Unitary dönüşümle temsil edilebilir bir işlemdir $U $ \begin{hizalaması} U \ket{b_0 b_1 \cnoktalar b_ {n-1}} \ket{\psı} = \ket{b_0 b_1 \cnoktalar b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cnoktalar b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psı} & \textrm{otherwise} \end{Cases}, \end{hizalaması}; burada $V $ işlemin eylemini temsil eden bir Unitary dönüşümtür `oracle` .</span><span class="sxs-lookup"><span data-stu-id="865cb-107">The output of this function is an operation that can be represented by a unitary transformation $U$ such that \begin{align} U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\ \ket{\psi} & \textrm{otherwise} \end{cases}, \end{align} where $V$ is a unitary transformation that represents the action of the `oracle` operation.</span></span>

## <a name="input"></a><span data-ttu-id="865cb-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="865cb-108">Input</span></span>

### <a name="bits--bool"></a><span data-ttu-id="865cb-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="865cb-109">bits : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="865cb-110">Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.</span><span class="sxs-lookup"><span data-stu-id="865cb-110">The bit string to control the given unitary operation on.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="865cb-111">Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="865cb-111">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="865cb-112">Hedef kaydına uygulanacak Unitary işlemi.</span><span class="sxs-lookup"><span data-stu-id="865cb-112">The unitary operation to be applied on the target register.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="865cb-113">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="865cb-113">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="865cb-114">`oracle`Denetim kayıt durumu bit maskesine karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işlemi `bits` .</span><span class="sxs-lookup"><span data-stu-id="865cb-114">A unitary operation that applies `oracle` on the target register if the control register state corresponds to the bit mask `bits`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="865cb-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="865cb-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="865cb-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="865cb-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="865cb-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="865cb-117">Remarks</span></span>

<span data-ttu-id="865cb-118">Tarafından verilen model `bits` öğesinden daha kısa olabilir `controlRegister` , bu durumda ek denetim qugeler yok sayılır (yani, $ \grex {0} veya $ \ket $ üzerinde denetlenmez {1} ).</span><span class="sxs-lookup"><span data-stu-id="865cb-118">The pattern given by `bits` may be shorter than `controlRegister`, in which case additional control qubits are ignored (that is, neither controlled on $\ket{0}$ nor $\ket{1}$).</span></span>
<span data-ttu-id="865cb-119">`bits`Daha uzunsa `controlRegister` bir hata oluşur.</span><span class="sxs-lookup"><span data-stu-id="865cb-119">If `bits` is longer than `controlRegister`, an error is raised.</span></span>

<span data-ttu-id="865cb-120">Bir Boole dizisi `bits` ve Unitary işlemi verildiğinde `oracle` , bu işlevin çıktısı aşağıdaki adımları gerçekleştiren bir işlemdir:</span><span class="sxs-lookup"><span data-stu-id="865cb-120">Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function is an operation that performs the following steps:</span></span>

* <span data-ttu-id="865cb-121">`X`öğesinin öğesine karşılık gelen denetim yazmacın her bir qubit öğesine bir işlem uygulayın `false` `bits` .</span><span class="sxs-lookup"><span data-stu-id="865cb-121">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits`;</span></span>
* <span data-ttu-id="865cb-122">`Controlled oracle`Denetim ve hedef Yazmaçları için geçerlidir;</span><span class="sxs-lookup"><span data-stu-id="865cb-122">apply `Controlled oracle` to the control and target registers;</span></span>
* <span data-ttu-id="865cb-123">`X` `false` `bits` denetim kaydını özgün durumuna döndürmek için, tekrar öğesine karşılık gelen denetim yazmacın her bir qubit öğesine bir işlem uygulayın.</span><span class="sxs-lookup"><span data-stu-id="865cb-123">apply an `X` operation to each qubit of the control register that corresponds to `false` element of the `bits` again to return the control register to the original state.</span></span>

<span data-ttu-id="865cb-124">Functor çıkışı, `Controlled` öğesinin nereden eşit olduğu özel bir durumdur `ControlledOnBitString` `bits` `[true, ..., true]` .</span><span class="sxs-lookup"><span data-stu-id="865cb-124">The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.</span></span>