---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoeachındexca işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850790"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="9ee92-102">Applytoeachındexca işlemi</span><span class="sxs-lookup"><span data-stu-id="9ee92-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="9ee92-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ee92-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ee92-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ee92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ee92-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="9ee92-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="9ee92-106">Değiştirici, `CA` tek qubit işleminin adjointable ve denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="9ee92-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9ee92-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="9ee92-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="9ee92-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="9ee92-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9ee92-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="9ee92-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9ee92-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="9ee92-110">register : 'T[]</span></span>

<span data-ttu-id="9ee92-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="9ee92-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ee92-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ee92-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ee92-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9ee92-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ee92-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9ee92-114">'T</span></span>

<span data-ttu-id="9ee92-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="9ee92-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ee92-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ee92-116">See Also</span></span>

- [<span data-ttu-id="9ee92-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="9ee92-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)