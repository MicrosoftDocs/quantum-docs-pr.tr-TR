---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850504"
---
# <a name="applytorest-operation"></a><span data-ttu-id="9a5c1-102">ApplyToRest işlemi</span><span class="sxs-lookup"><span data-stu-id="9a5c1-102">ApplyToRest operation</span></span>

<span data-ttu-id="9a5c1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a5c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a5c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9a5c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9a5c1-105">Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.</span><span class="sxs-lookup"><span data-stu-id="9a5c1-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9a5c1-106">Description</span><span class="sxs-lookup"><span data-stu-id="9a5c1-106">Description</span></span>

<span data-ttu-id="9a5c1-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9a5c1-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9a5c1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="9a5c1-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="9a5c1-109">Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a5c1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9a5c1-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="9a5c1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9a5c1-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="9a5c1-111">targets : 'T[]</span></span>

<span data-ttu-id="9a5c1-112">Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .</span><span class="sxs-lookup"><span data-stu-id="9a5c1-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a5c1-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a5c1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a5c1-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9a5c1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a5c1-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9a5c1-115">'T</span></span>

<span data-ttu-id="9a5c1-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="9a5c1-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="9a5c1-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="9a5c1-117">Example</span></span>

<span data-ttu-id="9a5c1-118">Aşağıdaki Q # parçacıkları eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="9a5c1-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="9a5c1-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9a5c1-119">See Also</span></span>

- [<span data-ttu-id="9a5c1-120">Microsoft. hisse. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="9a5c1-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="9a5c1-121">Microsoft. hisse. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="9a5c1-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="9a5c1-122">Microsoft. hisse. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="9a5c1-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)