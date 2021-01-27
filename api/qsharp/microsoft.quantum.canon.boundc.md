---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841037"
---
# <a name="boundc-function"></a><span data-ttu-id="5b329-102">BoundC işlevi</span><span class="sxs-lookup"><span data-stu-id="5b329-102">BoundC function</span></span>

<span data-ttu-id="5b329-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5b329-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5b329-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b329-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b329-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5b329-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="5b329-106">Değiştirici `C` dizideki tüm işlemlerin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="5b329-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="5b329-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5b329-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="5b329-108">işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="5b329-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="5b329-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="5b329-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="5b329-110">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="5b329-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="5b329-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="5b329-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5b329-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5b329-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b329-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5b329-113">'T</span></span>

<span data-ttu-id="5b329-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="5b329-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="5b329-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="5b329-115">Example</span></span>

<span data-ttu-id="5b329-116">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="5b329-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="5b329-117">ve</span><span class="sxs-lookup"><span data-stu-id="5b329-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="5b329-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5b329-118">See Also</span></span>

- [<span data-ttu-id="5b329-119">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="5b329-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)