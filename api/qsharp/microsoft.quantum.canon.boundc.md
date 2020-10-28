---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728915"
---
# <a name="boundc-function"></a><span data-ttu-id="7a853-102">BoundC işlevi</span><span class="sxs-lookup"><span data-stu-id="7a853-102">BoundC function</span></span>

<span data-ttu-id="7a853-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a853-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a853-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7a853-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7a853-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="7a853-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="7a853-106">Değiştirici `C` dizideki tüm işlemlerin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="7a853-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="7a853-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="7a853-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="7a853-108">işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL []</span><span class="sxs-lookup"><span data-stu-id="7a853-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="7a853-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="7a853-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="7a853-110">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="7a853-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="7a853-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="7a853-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7a853-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7a853-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a853-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7a853-113">'T</span></span>

<span data-ttu-id="7a853-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="7a853-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a853-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7a853-115">See Also</span></span>

- [<span data-ttu-id="7a853-116">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="7a853-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)