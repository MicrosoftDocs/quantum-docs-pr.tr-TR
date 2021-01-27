---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844524"
---
# <a name="boundca-function"></a><span data-ttu-id="79219-102">BoundCA işlevi</span><span class="sxs-lookup"><span data-stu-id="79219-102">BoundCA function</span></span>

<span data-ttu-id="79219-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79219-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79219-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79219-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79219-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="79219-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="79219-106">Değiştirici `CA` dizideki tüm işlemlerin adjointable ve denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="79219-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="79219-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="79219-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="79219-108">işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []</span><span class="sxs-lookup"><span data-stu-id="79219-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="79219-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="79219-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="79219-110">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="79219-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="79219-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="79219-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="79219-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="79219-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79219-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="79219-113">'T</span></span>

<span data-ttu-id="79219-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="79219-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="79219-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="79219-115">Example</span></span>

<span data-ttu-id="79219-116">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="79219-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="79219-117">ve</span><span class="sxs-lookup"><span data-stu-id="79219-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="79219-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="79219-118">See Also</span></span>

- [<span data-ttu-id="79219-119">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="79219-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)