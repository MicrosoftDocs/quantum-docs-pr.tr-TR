---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217807"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="777fa-102">ApplyToEachA işlemi</span><span class="sxs-lookup"><span data-stu-id="777fa-102">ApplyToEachA operation</span></span>

<span data-ttu-id="777fa-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="777fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="777fa-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="777fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="777fa-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="777fa-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="777fa-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="777fa-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="777fa-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="777fa-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="777fa-108">singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="777fa-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="777fa-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="777fa-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="777fa-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="777fa-110">register : 'T[]</span></span>

<span data-ttu-id="777fa-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="777fa-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="777fa-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="777fa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="777fa-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="777fa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="777fa-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="777fa-114">'T</span></span>

<span data-ttu-id="777fa-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="777fa-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="777fa-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="777fa-116">See Also</span></span>

- [<span data-ttu-id="777fa-117">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="777fa-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)