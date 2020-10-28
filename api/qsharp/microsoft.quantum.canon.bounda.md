---
uid: Microsoft.Quantum.Canon.BoundA
title: Sını işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728922"
---
# <a name="bounda-function"></a><span data-ttu-id="3dcda-102">Sını işlevi</span><span class="sxs-lookup"><span data-stu-id="3dcda-102">BoundA function</span></span>

<span data-ttu-id="3dcda-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3dcda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3dcda-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3dcda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3dcda-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3dcda-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="3dcda-106">Değiştirici `A` dizideki tüm işlemlerin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3dcda-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="3dcda-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="3dcda-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="3dcda-108">işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması []</span><span class="sxs-lookup"><span data-stu-id="3dcda-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="3dcda-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="3dcda-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="3dcda-110">Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="3dcda-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="3dcda-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3dcda-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3dcda-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3dcda-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3dcda-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3dcda-113">'T</span></span>

<span data-ttu-id="3dcda-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="3dcda-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="3dcda-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3dcda-115">See Also</span></span>

- [<span data-ttu-id="3dcda-116">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="3dcda-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)