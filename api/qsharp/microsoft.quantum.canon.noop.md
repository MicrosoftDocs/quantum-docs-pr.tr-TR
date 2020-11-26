---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205975"
---
# <a name="noop-operation"></a><span data-ttu-id="9a28d-102">NoOp işlemi</span><span class="sxs-lookup"><span data-stu-id="9a28d-102">NoOp operation</span></span>

<span data-ttu-id="9a28d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a28d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a28d-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9a28d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9a28d-105">Bir bağımsız değişkende kimlik işlemini (No-Op) gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="9a28d-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9a28d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9a28d-106">Description</span></span>

<span data-ttu-id="9a28d-107">Bu işlem herhangi bir türde bir değer alır ve bir şey yapmaz.</span><span class="sxs-lookup"><span data-stu-id="9a28d-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="9a28d-108">Bu, bir işlem türü girişi beklendiğinde yararlı olabilir, ancak hiçbir işlem gerçekleştirilmez.</span><span class="sxs-lookup"><span data-stu-id="9a28d-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="9a28d-109">Örneğin, belirli bir hata düzeltmesi sendromu hata oluştuğunu gösteriyorsa, `NoOp<Qubit[]>` doğru kurtarma yordamı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9a28d-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="9a28d-110">Benzer şekilde, bir işlem giriş olarak bir durum hazırlama yordamı beklediğinde, `NoOp<Qubit[]>` $ \ket{0 \cnoktalar 0} $ durumunu hazırlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9a28d-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="9a28d-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="9a28d-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="9a28d-112">Giriş: 'T</span><span class="sxs-lookup"><span data-stu-id="9a28d-112">input : 'T</span></span>

<span data-ttu-id="9a28d-113">Yok sayılacak bir değer.</span><span class="sxs-lookup"><span data-stu-id="9a28d-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a28d-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a28d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a28d-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9a28d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a28d-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9a28d-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="9a28d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9a28d-117">Remarks</span></span>

<span data-ttu-id="9a28d-118">Neredeyse her durumda, için tür parametresinin `NoOp` açıkça belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="9a28d-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="9a28d-119">Örneğin, `NoOp<Qubit>` ile aynıdır <xref:microsoft.quantum.intrinsic.i> .</span><span class="sxs-lookup"><span data-stu-id="9a28d-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a28d-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9a28d-120">See Also</span></span>

- [<span data-ttu-id="9a28d-121">Microsoft. hisse. Iç. I</span><span class="sxs-lookup"><span data-stu-id="9a28d-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)