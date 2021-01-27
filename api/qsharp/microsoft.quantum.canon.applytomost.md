---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Applytoen işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850600"
---
# <a name="applytomost-operation"></a><span data-ttu-id="3da2e-102">Applytoen işlem</span><span class="sxs-lookup"><span data-stu-id="3da2e-102">ApplyToMost operation</span></span>

<span data-ttu-id="3da2e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3da2e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3da2e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3da2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3da2e-105">Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.</span><span class="sxs-lookup"><span data-stu-id="3da2e-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="3da2e-106">Description</span><span class="sxs-lookup"><span data-stu-id="3da2e-106">Description</span></span>

<span data-ttu-id="3da2e-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="3da2e-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="3da2e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="3da2e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="3da2e-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3da2e-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3da2e-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3da2e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="3da2e-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="3da2e-111">targets : 'T[]</span></span>

<span data-ttu-id="3da2e-112">Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .</span><span class="sxs-lookup"><span data-stu-id="3da2e-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3da2e-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3da2e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3da2e-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3da2e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3da2e-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3da2e-115">'T</span></span>

<span data-ttu-id="3da2e-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="3da2e-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="3da2e-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="3da2e-117">Example</span></span>

<span data-ttu-id="3da2e-118">Aşağıdaki Q # parçacıkları eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3da2e-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="3da2e-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3da2e-119">See Also</span></span>

- [<span data-ttu-id="3da2e-120">Microsoft. hisse. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="3da2e-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="3da2e-121">Microsoft. hisse. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="3da2e-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="3da2e-122">Microsoft. hisse. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="3da2e-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)