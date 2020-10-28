---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729084"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="f2a37-102">ApplyToRestCA işlemi</span><span class="sxs-lookup"><span data-stu-id="f2a37-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="f2a37-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f2a37-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f2a37-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2a37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2a37-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="f2a37-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="f2a37-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f2a37-106">Description</span></span>

<span data-ttu-id="f2a37-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f2a37-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f2a37-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f2a37-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="f2a37-109">Op: 'T [] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="f2a37-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f2a37-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="f2a37-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f2a37-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="f2a37-111">targets : 'T[]</span></span>

<span data-ttu-id="f2a37-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="f2a37-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2a37-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2a37-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f2a37-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f2a37-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f2a37-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f2a37-115">'T</span></span>

<span data-ttu-id="f2a37-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="f2a37-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2a37-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f2a37-117">See Also</span></span>

- [<span data-ttu-id="f2a37-118">Microsoft. hisse. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="f2a37-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="f2a37-119">Microsoft. hisse. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="f2a37-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="f2a37-120">Microsoft. hisse. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="f2a37-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)