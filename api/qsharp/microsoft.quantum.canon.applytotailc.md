---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyTo, c işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217297"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="96e38-102">ApplyTo, c işlemi</span><span class="sxs-lookup"><span data-stu-id="96e38-102">ApplyToTailC operation</span></span>

<span data-ttu-id="96e38-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="96e38-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="96e38-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96e38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="96e38-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="96e38-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="96e38-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="96e38-106">Description</span></span>

<span data-ttu-id="96e38-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="96e38-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="96e38-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="96e38-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="96e38-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="96e38-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="96e38-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="96e38-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="96e38-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="96e38-111">targets : 'T[]</span></span>

<span data-ttu-id="96e38-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="96e38-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="96e38-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="96e38-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="96e38-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="96e38-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96e38-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="96e38-115">'T</span></span>

<span data-ttu-id="96e38-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="96e38-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="96e38-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="96e38-117">See Also</span></span>

- [<span data-ttu-id="96e38-118">Microsoft. hisse. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="96e38-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="96e38-119">Microsoft. hisse. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="96e38-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="96e38-120">Microsoft. hisse. Canon. Applytobir CA</span><span class="sxs-lookup"><span data-stu-id="96e38-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)