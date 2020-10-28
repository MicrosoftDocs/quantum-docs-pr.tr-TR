---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729096"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="ea404-102">ApplyToRestC işlemi</span><span class="sxs-lookup"><span data-stu-id="ea404-102">ApplyToRestC operation</span></span>

<span data-ttu-id="ea404-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ea404-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ea404-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea404-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea404-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="ea404-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ea404-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ea404-106">Description</span></span>

<span data-ttu-id="ea404-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ea404-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ea404-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ea404-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="ea404-109">Op: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ea404-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ea404-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ea404-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ea404-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="ea404-111">targets : 'T[]</span></span>

<span data-ttu-id="ea404-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="ea404-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea404-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea404-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ea404-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ea404-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ea404-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ea404-115">'T</span></span>

<span data-ttu-id="ea404-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="ea404-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea404-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ea404-117">See Also</span></span>

- [<span data-ttu-id="ea404-118">Microsoft. hisse. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="ea404-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="ea404-119">Microsoft. hisse. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="ea404-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="ea404-120">Microsoft. hisse. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="ea404-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)