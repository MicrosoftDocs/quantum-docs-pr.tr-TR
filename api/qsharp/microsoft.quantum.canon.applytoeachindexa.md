---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Applytoeachındexa işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850837"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="a2a32-102">Applytoeachındexa işlemi</span><span class="sxs-lookup"><span data-stu-id="a2a32-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="a2a32-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a2a32-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a2a32-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a2a32-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a2a32-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="a2a32-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="a2a32-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="a2a32-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a2a32-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="a2a32-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="a2a32-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="a2a32-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a2a32-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="a2a32-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="a2a32-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="a2a32-110">register : 'T[]</span></span>

<span data-ttu-id="a2a32-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="a2a32-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2a32-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2a32-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a2a32-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a2a32-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a2a32-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a2a32-114">'T</span></span>

<span data-ttu-id="a2a32-115">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="a2a32-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2a32-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a2a32-116">See Also</span></span>

- [<span data-ttu-id="a2a32-117">Microsoft. hisse. Canon. Applytoeachındex</span><span class="sxs-lookup"><span data-stu-id="a2a32-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)