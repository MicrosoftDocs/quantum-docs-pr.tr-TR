---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoeachındexca işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: c5bb61aadbdaab9c74a3dcd418088c532b495ff5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729276"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="24417-102">Applytoeachındexca işlemi</span><span class="sxs-lookup"><span data-stu-id="24417-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="24417-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24417-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24417-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24417-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24417-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="24417-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="24417-106">Değiştirici, `CA` tek qubit işleminin adjointable ve denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="24417-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="24417-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="24417-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj--ctl"></a><span data-ttu-id="24417-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="24417-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="24417-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="24417-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="24417-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="24417-110">register : 'T[]</span></span>

<span data-ttu-id="24417-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="24417-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24417-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24417-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="24417-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="24417-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24417-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="24417-114">'T</span></span>

<span data-ttu-id="24417-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="24417-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="24417-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="24417-116">See Also</span></span>

- [<span data-ttu-id="24417-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="24417-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)