---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 61dda69751989ef8a98fa8fb01d832014ec4ad35
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844633"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="24c16-102">ApplyToEach işlemi</span><span class="sxs-lookup"><span data-stu-id="24c16-102">ApplyToEach operation</span></span>

<span data-ttu-id="24c16-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="24c16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="24c16-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24c16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24c16-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="24c16-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="24c16-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="24c16-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="24c16-107">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24c16-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="24c16-108">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="24c16-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="24c16-109">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="24c16-109">register : 'T[]</span></span>

<span data-ttu-id="24c16-110">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="24c16-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="24c16-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="24c16-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="24c16-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="24c16-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="24c16-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="24c16-113">'T</span></span>

<span data-ttu-id="24c16-114">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="24c16-114">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="24c16-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="24c16-115">Example</span></span>

<span data-ttu-id="24c16-116">Üç-qubit $ \ket{+} $ durumu hazırlayın:</span><span class="sxs-lookup"><span data-stu-id="24c16-116">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="24c16-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="24c16-117">See Also</span></span>

- [<span data-ttu-id="24c16-118">Microsoft. hisse. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="24c16-118">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="24c16-119">Microsoft. hisse. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="24c16-119">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="24c16-120">Microsoft. hisse. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="24c16-120">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)