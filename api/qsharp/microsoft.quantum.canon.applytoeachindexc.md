---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Applytoeachındexc işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729282"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="694cf-102">Applytoeachındexc işlemi</span><span class="sxs-lookup"><span data-stu-id="694cf-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="694cf-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="694cf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="694cf-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="694cf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="694cf-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="694cf-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="694cf-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="694cf-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="694cf-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="694cf-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-ctl"></a><span data-ttu-id="694cf-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="694cf-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="694cf-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="694cf-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="694cf-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="694cf-110">register : 'T[]</span></span>

<span data-ttu-id="694cf-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="694cf-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="694cf-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="694cf-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="694cf-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="694cf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="694cf-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="694cf-114">'T</span></span>

<span data-ttu-id="694cf-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="694cf-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="694cf-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="694cf-116">See Also</span></span>

- [<span data-ttu-id="694cf-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="694cf-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)