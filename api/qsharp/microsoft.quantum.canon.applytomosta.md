---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208508"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="67053-102">ApplyToMostA işlemi</span><span class="sxs-lookup"><span data-stu-id="67053-102">ApplyToMostA operation</span></span>

<span data-ttu-id="67053-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67053-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67053-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67053-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67053-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="67053-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="67053-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="67053-106">Description</span></span>

<span data-ttu-id="67053-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="67053-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="67053-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="67053-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="67053-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="67053-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="67053-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="67053-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="67053-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="67053-111">targets : 'T[]</span></span>

<span data-ttu-id="67053-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="67053-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67053-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67053-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="67053-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="67053-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67053-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="67053-115">'T</span></span>

<span data-ttu-id="67053-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="67053-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="67053-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="67053-117">See Also</span></span>

- [<span data-ttu-id="67053-118">Microsoft. hisse. Canon. Applytoen</span><span class="sxs-lookup"><span data-stu-id="67053-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="67053-119">Microsoft. hisse. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="67053-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="67053-120">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="67053-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)