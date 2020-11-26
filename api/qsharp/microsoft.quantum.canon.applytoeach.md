---
uid: Microsoft.Quantum.Canon.ApplyToEach
title: ApplyToEach işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEach
qsharp.summary: Applies a single-qubit operation to each element in a register.
ms.openlocfilehash: 11f9363feb38676df3f805496c74036aa96160c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217875"
---
# <a name="applytoeach-operation"></a><span data-ttu-id="e90e5-102">ApplyToEach işlemi</span><span class="sxs-lookup"><span data-stu-id="e90e5-102">ApplyToEach operation</span></span>

<span data-ttu-id="e90e5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e90e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e90e5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e90e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e90e5-105">Bir kayıttaki her öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="e90e5-105">Applies a single-qubit operation to each element in a register.</span></span>

```qsharp
operation ApplyToEach<'T> (singleElementOperation : ('T => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e90e5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e90e5-106">Input</span></span>

### <a name="singleelementoperation--t--unit"></a><span data-ttu-id="e90e5-107">singleElementOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e90e5-107">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e90e5-108">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="e90e5-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="e90e5-109">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="e90e5-109">register : 'T[]</span></span>

<span data-ttu-id="e90e5-110">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="e90e5-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e90e5-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e90e5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e90e5-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e90e5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e90e5-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e90e5-113">'T</span></span>

<span data-ttu-id="e90e5-114">İşlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="e90e5-114">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e90e5-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e90e5-115">See Also</span></span>

- [<span data-ttu-id="e90e5-116">Microsoft. hisse. Canon. ApplyToEachC</span><span class="sxs-lookup"><span data-stu-id="e90e5-116">Microsoft.Quantum.Canon.ApplyToEachC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachC)
- [<span data-ttu-id="e90e5-117">Microsoft. hisse. Canon. ApplyToEachA</span><span class="sxs-lookup"><span data-stu-id="e90e5-117">Microsoft.Quantum.Canon.ApplyToEachA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachA)
- [<span data-ttu-id="e90e5-118">Microsoft. hisse. Canon. ApplyToEachCA</span><span class="sxs-lookup"><span data-stu-id="e90e5-118">Microsoft.Quantum.Canon.ApplyToEachCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachCA)