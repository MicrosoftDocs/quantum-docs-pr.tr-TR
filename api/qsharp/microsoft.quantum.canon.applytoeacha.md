---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: ApplyToEachA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844613"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="adc9b-102">ApplyToEachA işlemi</span><span class="sxs-lookup"><span data-stu-id="adc9b-102">ApplyToEachA operation</span></span>

<span data-ttu-id="adc9b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="adc9b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="adc9b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adc9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adc9b-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="adc9b-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="adc9b-106">Değiştirici, `A` tek qubit işleminin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="adc9b-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="adc9b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="adc9b-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="adc9b-108">singleElementOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="adc9b-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="adc9b-109">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="adc9b-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="adc9b-110">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="adc9b-110">register : 'T[]</span></span>

<span data-ttu-id="adc9b-111">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="adc9b-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="adc9b-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="adc9b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="adc9b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="adc9b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="adc9b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="adc9b-114">'T</span></span>

<span data-ttu-id="adc9b-115">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="adc9b-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="adc9b-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="adc9b-116">Example</span></span>

<span data-ttu-id="adc9b-117">Üç-qubit $ \ket{+} $ durumu hazırlayın:</span><span class="sxs-lookup"><span data-stu-id="adc9b-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="adc9b-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="adc9b-118">See Also</span></span>

- [<span data-ttu-id="adc9b-119">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="adc9b-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)