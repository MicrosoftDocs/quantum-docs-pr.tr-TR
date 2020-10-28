---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Applytobir CA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 00755df80981a09ddfd8327ee9b35761d30af4f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729030"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="ce5c0-102">Applytobir CA işlemi</span><span class="sxs-lookup"><span data-stu-id="ce5c0-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="ce5c0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce5c0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce5c0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce5c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce5c0-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="ce5c0-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ce5c0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce5c0-106">Description</span></span>

<span data-ttu-id="ce5c0-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ce5c0-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ce5c0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce5c0-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="ce5c0-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="ce5c0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ce5c0-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ce5c0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ce5c0-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="ce5c0-111">targets : 'T[]</span></span>

<span data-ttu-id="ce5c0-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="ce5c0-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce5c0-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce5c0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ce5c0-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ce5c0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce5c0-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ce5c0-115">'T</span></span>

<span data-ttu-id="ce5c0-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="ce5c0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce5c0-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ce5c0-117">See Also</span></span>

- [<span data-ttu-id="ce5c0-118">Microsoft. hisse. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="ce5c0-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="ce5c0-119">Microsoft. hisse. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="ce5c0-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="ce5c0-120">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="ce5c0-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)