---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Applytoeachındexa işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 0fe0697e6f1d9441c2d2ad2c7396f6da8daa0e1e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729287"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="27d85-102">Applytoeachındexa işlemi</span><span class="sxs-lookup"><span data-stu-id="27d85-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="27d85-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27d85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27d85-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27d85-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27d85-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="27d85-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="27d85-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="27d85-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="27d85-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="27d85-107">Input</span></span>

### <a name="singleelementoperation--intt--unit-adj"></a><span data-ttu-id="27d85-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="27d85-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="27d85-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="27d85-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="27d85-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="27d85-110">register : 'T[]</span></span>

<span data-ttu-id="27d85-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="27d85-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27d85-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27d85-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27d85-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="27d85-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27d85-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="27d85-114">'T</span></span>

<span data-ttu-id="27d85-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="27d85-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="27d85-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="27d85-116">See Also</span></span>

- [<span data-ttu-id="27d85-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="27d85-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)