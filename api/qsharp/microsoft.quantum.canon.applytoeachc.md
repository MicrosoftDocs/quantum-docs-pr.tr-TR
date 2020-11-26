---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217790"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="881de-102">ApplyToEachC işlemi</span><span class="sxs-lookup"><span data-stu-id="881de-102">ApplyToEachC operation</span></span>

<span data-ttu-id="881de-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="881de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="881de-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="881de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="881de-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="881de-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="881de-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="881de-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="881de-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="881de-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="881de-108">singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="881de-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="881de-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="881de-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="881de-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="881de-110">register : 'T[]</span></span>

<span data-ttu-id="881de-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="881de-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="881de-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="881de-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="881de-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="881de-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="881de-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="881de-114">'T</span></span>

<span data-ttu-id="881de-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="881de-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="881de-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="881de-116">See Also</span></span>

- [<span data-ttu-id="881de-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="881de-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)