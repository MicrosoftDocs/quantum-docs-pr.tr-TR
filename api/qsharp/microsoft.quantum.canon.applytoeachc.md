---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850848"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="94ee4-102">ApplyToEachC işlemi</span><span class="sxs-lookup"><span data-stu-id="94ee4-102">ApplyToEachC operation</span></span>

<span data-ttu-id="94ee4-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94ee4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94ee4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94ee4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94ee4-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="94ee4-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="94ee4-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="94ee4-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="94ee4-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="94ee4-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="94ee4-108">singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="94ee4-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="94ee4-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="94ee4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="94ee4-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="94ee4-110">register : 'T[]</span></span>

<span data-ttu-id="94ee4-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="94ee4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94ee4-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94ee4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94ee4-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="94ee4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94ee4-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="94ee4-114">'T</span></span>

<span data-ttu-id="94ee4-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="94ee4-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="94ee4-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="94ee4-116">Example</span></span>

<span data-ttu-id="94ee4-117">Üç-qubit $ \ket{+} $ durumu hazırlayın:</span><span class="sxs-lookup"><span data-stu-id="94ee4-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="94ee4-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="94ee4-118">See Also</span></span>

- [<span data-ttu-id="94ee4-119">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="94ee4-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)