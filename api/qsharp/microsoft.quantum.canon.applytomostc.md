---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850554"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="92758-102">ApplyToMostC işlemi</span><span class="sxs-lookup"><span data-stu-id="92758-102">ApplyToMostC operation</span></span>

<span data-ttu-id="92758-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92758-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92758-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92758-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92758-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="92758-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="92758-106">Description</span><span class="sxs-lookup"><span data-stu-id="92758-106">Description</span></span>

<span data-ttu-id="92758-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="92758-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="92758-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="92758-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="92758-109">Op: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="92758-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="92758-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="92758-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="92758-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="92758-111">targets : 'T[]</span></span>

<span data-ttu-id="92758-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="92758-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92758-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92758-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="92758-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="92758-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="92758-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="92758-115">'T</span></span>

<span data-ttu-id="92758-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="92758-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="92758-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="92758-117">See Also</span></span>

- [<span data-ttu-id="92758-118">Microsoft. hisse. Canon. Applytoen</span><span class="sxs-lookup"><span data-stu-id="92758-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="92758-119">Microsoft. hisse. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="92758-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="92758-120">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="92758-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)