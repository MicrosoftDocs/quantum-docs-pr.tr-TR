---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: dfa18b6eb7a2c42fa2982994a2fc92170b52599c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729299"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="70402-102">ApplyToEachC işlemi</span><span class="sxs-lookup"><span data-stu-id="70402-102">ApplyToEachC operation</span></span>

<span data-ttu-id="70402-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70402-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70402-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70402-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70402-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="70402-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="70402-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="70402-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="70402-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="70402-107">Input</span></span>

### <a name="singleelementoperation--t--unit-ctl"></a><span data-ttu-id="70402-108">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="70402-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="70402-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="70402-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="70402-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="70402-110">register : 'T[]</span></span>

<span data-ttu-id="70402-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="70402-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="70402-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="70402-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="70402-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="70402-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70402-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="70402-114">'T</span></span>

<span data-ttu-id="70402-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="70402-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="70402-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70402-116">See Also</span></span>

- [<span data-ttu-id="70402-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="70402-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)