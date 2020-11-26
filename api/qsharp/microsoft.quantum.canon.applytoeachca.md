---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217756"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="f5250-102">ApplyToEachCA işlemi</span><span class="sxs-lookup"><span data-stu-id="f5250-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="f5250-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f5250-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f5250-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f5250-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f5250-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="f5250-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="f5250-106">Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f5250-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f5250-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f5250-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="f5250-108">singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="f5250-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f5250-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="f5250-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f5250-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="f5250-110">register : 'T[]</span></span>

<span data-ttu-id="f5250-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="f5250-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5250-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5250-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f5250-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f5250-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f5250-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f5250-114">'T</span></span>

<span data-ttu-id="f5250-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="f5250-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5250-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f5250-116">See Also</span></span>

- [<span data-ttu-id="f5250-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="f5250-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)