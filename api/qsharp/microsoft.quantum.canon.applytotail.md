---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850449"
---
# <a name="applytotail-operation"></a><span data-ttu-id="59e6e-102">ApplyToTail işlemi</span><span class="sxs-lookup"><span data-stu-id="59e6e-102">ApplyToTail operation</span></span>

<span data-ttu-id="59e6e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59e6e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59e6e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59e6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59e6e-105">Bir işlemi bir dizinin son öğesine uygular.</span><span class="sxs-lookup"><span data-stu-id="59e6e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="59e6e-106">Description</span><span class="sxs-lookup"><span data-stu-id="59e6e-106">Description</span></span>

<span data-ttu-id="59e6e-107">Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="59e6e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="59e6e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="59e6e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="59e6e-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59e6e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="59e6e-110">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="59e6e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="59e6e-111">hedefler: 'T []</span><span class="sxs-lookup"><span data-stu-id="59e6e-111">targets : 'T[]</span></span>

<span data-ttu-id="59e6e-112">En son uygulanacak hedefler dizisi `op` .</span><span class="sxs-lookup"><span data-stu-id="59e6e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59e6e-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59e6e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59e6e-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="59e6e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59e6e-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="59e6e-115">'T</span></span>

<span data-ttu-id="59e6e-116">Uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="59e6e-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="59e6e-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="59e6e-117">Example</span></span>

<span data-ttu-id="59e6e-118">Aşağıdaki Q # parçacıkları eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="59e6e-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="59e6e-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="59e6e-119">See Also</span></span>

- [<span data-ttu-id="59e6e-120">Microsoft. hisse. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="59e6e-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="59e6e-121">Microsoft. hisse. Canon. ApplyTo, c</span><span class="sxs-lookup"><span data-stu-id="59e6e-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="59e6e-122">Microsoft. hisse. Canon. Applytobir CA</span><span class="sxs-lookup"><span data-stu-id="59e6e-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)