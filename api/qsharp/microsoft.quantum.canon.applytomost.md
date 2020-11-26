---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Applytoen işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7e7824b431ccff644cf5cc53145163327eb8ad36
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208542"
---
# <a name="applytomost-operation"></a><span data-ttu-id="2a9b9-102">Applytoen işlem</span><span class="sxs-lookup"><span data-stu-id="2a9b9-102">ApplyToMost operation</span></span>

<span data-ttu-id="2a9b9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a9b9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a9b9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a9b9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a9b9-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="2a9b9-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="2a9b9-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2a9b9-106">Description</span></span>

<span data-ttu-id="2a9b9-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2a9b9-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2a9b9-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a9b9-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="2a9b9-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a9b9-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2a9b9-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="2a9b9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2a9b9-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="2a9b9-111">targets : 'T[]</span></span>

<span data-ttu-id="2a9b9-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="2a9b9-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a9b9-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a9b9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2a9b9-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2a9b9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a9b9-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2a9b9-115">'T</span></span>

<span data-ttu-id="2a9b9-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="2a9b9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a9b9-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2a9b9-117">See Also</span></span>

- [<span data-ttu-id="2a9b9-118">Microsoft. hisse. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="2a9b9-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="2a9b9-119">Microsoft. hisse. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="2a9b9-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="2a9b9-120">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="2a9b9-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)