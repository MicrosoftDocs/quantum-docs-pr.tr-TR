---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: af55093e44ce023c9e8b7e478730f4c527cf6d32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208474"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="41f39-102">ApplyToMostC işlemi</span><span class="sxs-lookup"><span data-stu-id="41f39-102">ApplyToMostC operation</span></span>

<span data-ttu-id="41f39-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41f39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41f39-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41f39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41f39-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="41f39-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="41f39-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="41f39-106">Description</span></span>

<span data-ttu-id="41f39-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="41f39-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="41f39-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="41f39-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="41f39-109">Op: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="41f39-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="41f39-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="41f39-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="41f39-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="41f39-111">targets : 'T[]</span></span>

<span data-ttu-id="41f39-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="41f39-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41f39-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41f39-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41f39-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="41f39-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41f39-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="41f39-115">'T</span></span>

<span data-ttu-id="41f39-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="41f39-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="41f39-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="41f39-117">See Also</span></span>

- [<span data-ttu-id="41f39-118">Microsoft. hisse. Canon. Applytoen</span><span class="sxs-lookup"><span data-stu-id="41f39-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="41f39-119">Microsoft. hisse. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="41f39-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="41f39-120">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="41f39-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)