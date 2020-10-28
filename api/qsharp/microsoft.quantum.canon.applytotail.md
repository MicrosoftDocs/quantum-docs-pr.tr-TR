---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 72b55ec7161d5f6af5e4cb512c648078516c3b4e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729048"
---
# <a name="applytotail-operation"></a><span data-ttu-id="c2d74-102">ApplyToTail işlemi</span><span class="sxs-lookup"><span data-stu-id="c2d74-102">ApplyToTail operation</span></span>

<span data-ttu-id="c2d74-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2d74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2d74-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2d74-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2d74-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="c2d74-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c2d74-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c2d74-106">Description</span></span>

<span data-ttu-id="c2d74-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="c2d74-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c2d74-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c2d74-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="c2d74-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2d74-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2d74-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="c2d74-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c2d74-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="c2d74-111">targets : 'T[]</span></span>

<span data-ttu-id="c2d74-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="c2d74-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2d74-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2d74-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2d74-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c2d74-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2d74-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c2d74-115">'T</span></span>

<span data-ttu-id="c2d74-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="c2d74-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2d74-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c2d74-117">See Also</span></span>

- [<span data-ttu-id="c2d74-118">Microsoft. hisse. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="c2d74-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="c2d74-119">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="c2d74-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="c2d74-120">Microsoft. hisse. Canon. Applytobir CA</span><span class="sxs-lookup"><span data-stu-id="c2d74-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)