---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: e1625829e2e9efd9d39fe0692f01c1cbbffc651c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729311"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="9fc55-102">ApplyToEach işlemi</span><span class="sxs-lookup"><span data-stu-id="9fc55-102">ApplyToEach operation</span></span>

<span data-ttu-id="9fc55-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9fc55-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9fc55-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9fc55-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9fc55-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="9fc55-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9fc55-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9fc55-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="9fc55-107">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fc55-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9fc55-108">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="9fc55-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9fc55-109">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="9fc55-109">register : 'T[]</span></span>

<span data-ttu-id="9fc55-110">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="9fc55-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9fc55-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9fc55-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9fc55-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9fc55-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9fc55-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9fc55-113">'T</span></span>

<span data-ttu-id="9fc55-114">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="9fc55-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fc55-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9fc55-115">See Also</span></span>

- [<span data-ttu-id="9fc55-116">Microsoft. hisse. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="9fc55-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="9fc55-117">Microsoft. hisse. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="9fc55-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="9fc55-118">Microsoft. hisse. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="9fc55-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)