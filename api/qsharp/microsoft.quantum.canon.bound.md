---
uid: Microsoft.Quantum.Canon.Bound
title: Bağlantılı işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841060"
---
# <a name="bound-function"></a><span data-ttu-id="bd9da-102">Bağlantılı işlev</span><span class="sxs-lookup"><span data-stu-id="bd9da-102">Bound function</span></span>

<span data-ttu-id="bd9da-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bd9da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bd9da-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd9da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd9da-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bd9da-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="bd9da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bd9da-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="bd9da-107">işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="bd9da-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="bd9da-108">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="bd9da-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="bd9da-109">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bd9da-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bd9da-110">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="bd9da-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bd9da-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bd9da-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bd9da-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bd9da-112">'T</span></span>

<span data-ttu-id="bd9da-113">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="bd9da-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="bd9da-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="bd9da-114">Example</span></span>

<span data-ttu-id="bd9da-115">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="bd9da-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="bd9da-116">ve</span><span class="sxs-lookup"><span data-stu-id="bd9da-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="bd9da-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bd9da-117">See Also</span></span>

- [<span data-ttu-id="bd9da-118">Microsoft. hisse. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="bd9da-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="bd9da-119">Microsoft. hisse. Canon. sını</span><span class="sxs-lookup"><span data-stu-id="bd9da-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="bd9da-120">Microsoft. hisse. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="bd9da-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)