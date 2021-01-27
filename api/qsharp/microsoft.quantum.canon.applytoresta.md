---
uid: Microsoft.Quantum.Canon.ApplyToRestA
title: ApplyToRestA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 69001f6c8d65806e7259f2d2f2741d48866daa84
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841259"
---
# <a name="applytoresta-operation"></a><span data-ttu-id="91c98-102">ApplyToRestA işlemi</span><span class="sxs-lookup"><span data-stu-id="91c98-102">ApplyToRestA operation</span></span>

<span data-ttu-id="91c98-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91c98-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91c98-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91c98-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91c98-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="91c98-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="91c98-106">Description</span><span class="sxs-lookup"><span data-stu-id="91c98-106">Description</span></span>

<span data-ttu-id="91c98-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="91c98-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="91c98-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="91c98-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="91c98-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="91c98-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="91c98-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="91c98-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="91c98-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="91c98-111">targets : 'T[]</span></span>

<span data-ttu-id="91c98-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="91c98-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91c98-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91c98-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="91c98-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="91c98-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91c98-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="91c98-115">'T</span></span>

<span data-ttu-id="91c98-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="91c98-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="91c98-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="91c98-117">See Also</span></span>

- [<span data-ttu-id="91c98-118">Microsoft. hisse. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="91c98-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="91c98-119">Microsoft. hisse. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="91c98-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="91c98-120">Microsoft. hisse. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="91c98-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)