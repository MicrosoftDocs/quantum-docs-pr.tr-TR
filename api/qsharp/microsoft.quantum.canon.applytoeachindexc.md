---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Applytoeachındexc işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850817"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="2a50b-102">Applytoeachındexc işlemi</span><span class="sxs-lookup"><span data-stu-id="2a50b-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="2a50b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a50b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a50b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a50b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a50b-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="2a50b-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="2a50b-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="2a50b-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="2a50b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a50b-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="2a50b-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="2a50b-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="2a50b-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="2a50b-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2a50b-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="2a50b-110">register : 'T[]</span></span>

<span data-ttu-id="2a50b-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="2a50b-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a50b-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a50b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2a50b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2a50b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a50b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2a50b-114">'T</span></span>

<span data-ttu-id="2a50b-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="2a50b-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a50b-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2a50b-116">See Also</span></span>

- [<span data-ttu-id="2a50b-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="2a50b-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)