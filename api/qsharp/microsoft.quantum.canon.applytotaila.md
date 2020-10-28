---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729047"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="6b7be-102">ApplyToTailA işlemi</span><span class="sxs-lookup"><span data-stu-id="6b7be-102">ApplyToTailA operation</span></span>

<span data-ttu-id="6b7be-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b7be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b7be-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6b7be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6b7be-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="6b7be-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6b7be-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6b7be-106">Description</span></span>

<span data-ttu-id="6b7be-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="6b7be-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6b7be-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6b7be-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="6b7be-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="6b7be-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="6b7be-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6b7be-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6b7be-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="6b7be-111">targets : 'T[]</span></span>

<span data-ttu-id="6b7be-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="6b7be-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b7be-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b7be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b7be-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6b7be-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b7be-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6b7be-115">'T</span></span>

<span data-ttu-id="6b7be-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="6b7be-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b7be-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6b7be-117">See Also</span></span>

- [<span data-ttu-id="6b7be-118">Microsoft. hisse. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="6b7be-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="6b7be-119">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="6b7be-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="6b7be-120">Microsoft. hisse. Canon. Applytobir CA</span><span class="sxs-lookup"><span data-stu-id="6b7be-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)