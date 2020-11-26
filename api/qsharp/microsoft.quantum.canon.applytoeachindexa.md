---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Applytoeachındexa işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217603"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="f389a-102">Applytoeachındexa işlemi</span><span class="sxs-lookup"><span data-stu-id="f389a-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="f389a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f389a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f389a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f389a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f389a-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="f389a-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="f389a-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f389a-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f389a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f389a-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="f389a-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="f389a-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f389a-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="f389a-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="f389a-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="f389a-110">register : 'T[]</span></span>

<span data-ttu-id="f389a-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="f389a-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f389a-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f389a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f389a-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f389a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f389a-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f389a-114">'T</span></span>

<span data-ttu-id="f389a-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="f389a-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="f389a-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f389a-116">See Also</span></span>

- [<span data-ttu-id="f389a-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="f389a-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)