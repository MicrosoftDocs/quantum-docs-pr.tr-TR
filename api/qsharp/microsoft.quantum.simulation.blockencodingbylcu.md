---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229554"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="02f45-102">BlockEncodingByLCU işlevi</span><span class="sxs-lookup"><span data-stu-id="02f45-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="02f45-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="02f45-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="02f45-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02f45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02f45-105">Bir ilgilendiğiniz işleci bir ile kodluyor `BlockEncoding` .</span><span class="sxs-lookup"><span data-stu-id="02f45-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="02f45-106">Bu `BlockEncoding` , bazı işleci kodlayan bir Unitary $U = P\cdot V\cdot P ^ \dağılım $ oluşturur $H = \ sum_ {j} | \ alpha_j | U_j $ ilgi çekici bir şekilde oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="02f45-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="02f45-107">Genellikle $P $, $P {0} \_ \tusa = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ ve $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $ gibi bir durum hazırlama birimiyiydir.</span><span class="sxs-lookup"><span data-stu-id="02f45-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="02f45-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="02f45-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="02f45-109">Statehazırlama: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="02f45-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="02f45-110">Bazı hedef durumları hazırlayan bir Unitary $P $.</span><span class="sxs-lookup"><span data-stu-id="02f45-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="02f45-111">seçici: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="02f45-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="02f45-112">$H $ 'ın bileşen unitları 'nı kodlayan bir Unitary $V $.</span><span class="sxs-lookup"><span data-stu-id="02f45-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="02f45-113">Çıkış: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="02f45-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="02f45-114">Bir Unitary $U $, yazmaçlara `a` ve `s` Bu blok-kodlar $H $ $U ve bu da < \hanger = U $ karşılar.</span><span class="sxs-lookup"><span data-stu-id="02f45-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="02f45-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="02f45-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02f45-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="02f45-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="02f45-117">Üreticinin</span><span class="sxs-lookup"><span data-stu-id="02f45-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="02f45-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="02f45-118">Remarks</span></span>

<span data-ttu-id="02f45-119">Bu `BlockEncoding` uygulama, bunun özelliklerini verir `BlockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="02f45-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="02f45-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="02f45-120">See Also</span></span>

- [<span data-ttu-id="02f45-121">Microsoft. hisse. simülasyon. Blockenkodlama</span><span class="sxs-lookup"><span data-stu-id="02f45-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="02f45-122">Microsoft. hisse. simülasyon. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="02f45-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)