---
uid: Microsoft.Quantum.Canon.BoundA
title: Sını işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844535"
---
# <a name="bounda-function"></a><span data-ttu-id="fd13d-102">Sını işlevi</span><span class="sxs-lookup"><span data-stu-id="fd13d-102">BoundA function</span></span>

<span data-ttu-id="fd13d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fd13d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fd13d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd13d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd13d-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="fd13d-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="fd13d-106">Değiştirici `A` dizideki tüm işlemlerin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="fd13d-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="fd13d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="fd13d-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="fd13d-108">işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı []</span><span class="sxs-lookup"><span data-stu-id="fd13d-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="fd13d-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="fd13d-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="fd13d-110">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="fd13d-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="fd13d-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="fd13d-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fd13d-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="fd13d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fd13d-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="fd13d-113">'T</span></span>

<span data-ttu-id="fd13d-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="fd13d-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="fd13d-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="fd13d-115">Example</span></span>

<span data-ttu-id="fd13d-116">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fd13d-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

<span data-ttu-id="fd13d-117">ve</span><span class="sxs-lookup"><span data-stu-id="fd13d-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="fd13d-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fd13d-118">See Also</span></span>

- [<span data-ttu-id="fd13d-119">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="fd13d-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)