---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208423"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="eff65-102">ApplyToMostCA işlemi</span><span class="sxs-lookup"><span data-stu-id="eff65-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="eff65-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eff65-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eff65-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eff65-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eff65-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="eff65-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="eff65-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="eff65-106">Description</span></span>

<span data-ttu-id="eff65-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="eff65-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="eff65-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="eff65-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="eff65-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="eff65-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="eff65-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="eff65-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="eff65-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="eff65-111">targets : 'T[]</span></span>

<span data-ttu-id="eff65-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="eff65-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eff65-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eff65-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eff65-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eff65-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eff65-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eff65-115">'T</span></span>

<span data-ttu-id="eff65-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="eff65-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="eff65-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eff65-117">See Also</span></span>

- [<span data-ttu-id="eff65-118">Microsoft. hisse. Canon. Applytoen</span><span class="sxs-lookup"><span data-stu-id="eff65-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="eff65-119">Microsoft. hisse. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="eff65-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="eff65-120">Microsoft. hisse. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="eff65-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)