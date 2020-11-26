---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207590"
---
# <a name="boundc-function"></a><span data-ttu-id="c3e5a-102">BoundC işlevi</span><span class="sxs-lookup"><span data-stu-id="c3e5a-102">BoundC function</span></span>

<span data-ttu-id="c3e5a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3e5a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3e5a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3e5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3e5a-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="c3e5a-106">Değiştirici `C` dizideki tüm işlemlerin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c3e5a-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="c3e5a-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="c3e5a-108">işlemler: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL []</span><span class="sxs-lookup"><span data-stu-id="c3e5a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="c3e5a-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="c3e5a-110">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="c3e5a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c3e5a-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c3e5a-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c3e5a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3e5a-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c3e5a-113">'T</span></span>

<span data-ttu-id="c3e5a-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e5a-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c3e5a-115">See Also</span></span>

- [<span data-ttu-id="c3e5a-116">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="c3e5a-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)