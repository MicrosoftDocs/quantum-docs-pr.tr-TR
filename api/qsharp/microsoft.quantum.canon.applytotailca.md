---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Applytobir CA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207862"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="38a1c-102">Applytobir CA işlemi</span><span class="sxs-lookup"><span data-stu-id="38a1c-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="38a1c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38a1c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38a1c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38a1c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38a1c-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="38a1c-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="38a1c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="38a1c-106">Description</span></span>

<span data-ttu-id="38a1c-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="38a1c-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="38a1c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="38a1c-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="38a1c-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="38a1c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="38a1c-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="38a1c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="38a1c-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="38a1c-111">targets : 'T[]</span></span>

<span data-ttu-id="38a1c-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="38a1c-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38a1c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38a1c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="38a1c-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="38a1c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38a1c-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="38a1c-115">'T</span></span>

<span data-ttu-id="38a1c-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="38a1c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="38a1c-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="38a1c-117">See Also</span></span>

- [<span data-ttu-id="38a1c-118">Microsoft. hisse. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="38a1c-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="38a1c-119">Microsoft. hisse. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="38a1c-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="38a1c-120">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="38a1c-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)