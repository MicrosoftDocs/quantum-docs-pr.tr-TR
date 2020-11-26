---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207930"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="2b98b-102">ApplyToTailA işlemi</span><span class="sxs-lookup"><span data-stu-id="2b98b-102">ApplyToTailA operation</span></span>

<span data-ttu-id="2b98b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2b98b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2b98b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b98b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b98b-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="2b98b-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="2b98b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2b98b-106">Description</span></span>

<span data-ttu-id="2b98b-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2b98b-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2b98b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="2b98b-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="2b98b-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="2b98b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2b98b-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="2b98b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2b98b-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="2b98b-111">targets : 'T[]</span></span>

<span data-ttu-id="2b98b-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="2b98b-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2b98b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2b98b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2b98b-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="2b98b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2b98b-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="2b98b-115">'T</span></span>

<span data-ttu-id="2b98b-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="2b98b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b98b-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2b98b-117">See Also</span></span>

- [<span data-ttu-id="2b98b-118">Microsoft. hisse. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="2b98b-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="2b98b-119">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="2b98b-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="2b98b-120">Microsoft. hisse. Canon. Applytobir CA</span><span class="sxs-lookup"><span data-stu-id="2b98b-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)