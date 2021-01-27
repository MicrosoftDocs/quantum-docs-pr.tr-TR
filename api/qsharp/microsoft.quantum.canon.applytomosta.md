---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850581"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="533b1-102">ApplyToMostA işlemi</span><span class="sxs-lookup"><span data-stu-id="533b1-102">ApplyToMostA operation</span></span>

<span data-ttu-id="533b1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="533b1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="533b1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="533b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="533b1-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="533b1-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="533b1-106">Description</span><span class="sxs-lookup"><span data-stu-id="533b1-106">Description</span></span>

<span data-ttu-id="533b1-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="533b1-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="533b1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="533b1-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="533b1-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="533b1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="533b1-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="533b1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="533b1-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="533b1-111">targets : 'T[]</span></span>

<span data-ttu-id="533b1-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="533b1-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="533b1-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="533b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="533b1-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="533b1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="533b1-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="533b1-115">'T</span></span>

<span data-ttu-id="533b1-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="533b1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="533b1-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="533b1-117">See Also</span></span>

- [<span data-ttu-id="533b1-118">Microsoft. hisse. Canon. Applytoen</span><span class="sxs-lookup"><span data-stu-id="533b1-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="533b1-119">Microsoft. hisse. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="533b1-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="533b1-120">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="533b1-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)