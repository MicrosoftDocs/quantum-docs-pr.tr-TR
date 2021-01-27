---
uid: Microsoft.Quantum.Canon.ApplyToEachIndex
title: Applytoeachındex işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndex
qsharp.summary: Applies a single-qubit operation to each indexed element in a register.
ms.openlocfilehash: 8b34dc24580a3df7ae2c13ef87a6fa10c7afd3f8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844585"
---
# <a name="applytoeachindex-operation"></a><span data-ttu-id="9ea73-102">Applytoeachındex işlemi</span><span class="sxs-lookup"><span data-stu-id="9ea73-102">ApplyToEachIndex operation</span></span>

<span data-ttu-id="9ea73-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ea73-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ea73-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ea73-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ea73-105">Bir kayıttaki her dizinli öğeye bir tek qubit işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="9ea73-105">Applies a single-qubit operation to each indexed element in a register.</span></span>

```qsharp
operation ApplyToEachIndex<'T> (singleElementOperation : ((Int, 'T) => Unit), register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9ea73-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9ea73-106">Input</span></span>

### <a name="singleelementoperation--intt--unit"></a><span data-ttu-id="9ea73-107">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ea73-107">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9ea73-108">Her bir qubit için uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="9ea73-108">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="9ea73-109">kaydolun: 'T []</span><span class="sxs-lookup"><span data-stu-id="9ea73-109">register : 'T[]</span></span>

<span data-ttu-id="9ea73-110">Verilen işlemin uygulanacağı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="9ea73-110">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ea73-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ea73-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ea73-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9ea73-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ea73-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9ea73-113">'T</span></span>

<span data-ttu-id="9ea73-114">Her bir işlemin işlem gördüğü hedef.</span><span class="sxs-lookup"><span data-stu-id="9ea73-114">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ea73-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ea73-115">See Also</span></span>

- [<span data-ttu-id="9ea73-116">Microsoft. hisse. Canon. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="9ea73-116">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)
- [<span data-ttu-id="9ea73-117">Microsoft. hisse. Canon. Applytoeachındexa</span><span class="sxs-lookup"><span data-stu-id="9ea73-117">Microsoft.Quantum.Canon.ApplyToEachIndexA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexA)
- [<span data-ttu-id="9ea73-118">Microsoft. hisse. Canon. Applytoeachındexc</span><span class="sxs-lookup"><span data-stu-id="9ea73-118">Microsoft.Quantum.Canon.ApplyToEachIndexC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexC)
- [<span data-ttu-id="9ea73-119">Microsoft. hisse. Canon. Applytoeachındexca</span><span class="sxs-lookup"><span data-stu-id="9ea73-119">Microsoft.Quantum.Canon.ApplyToEachIndexCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndexCA)