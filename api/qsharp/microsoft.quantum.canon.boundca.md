---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728898"
---
# <a name="boundca-function"></a><span data-ttu-id="997ca-102">BoundCA işlevi</span><span class="sxs-lookup"><span data-stu-id="997ca-102">BoundCA function</span></span>

<span data-ttu-id="997ca-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="997ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="997ca-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="997ca-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="997ca-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="997ca-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="997ca-106">Değiştirici `CA` dizideki tüm işlemlerin adjointable ve denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="997ca-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="997ca-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="997ca-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="997ca-108">işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL []</span><span class="sxs-lookup"><span data-stu-id="997ca-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="997ca-109">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="997ca-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="997ca-110">Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="997ca-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="997ca-111">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="997ca-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="997ca-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="997ca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="997ca-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="997ca-113">'T</span></span>

<span data-ttu-id="997ca-114">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="997ca-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="997ca-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="997ca-115">See Also</span></span>

- [<span data-ttu-id="997ca-116">Microsoft. hisse. Canon. bağlanacak</span><span class="sxs-lookup"><span data-stu-id="997ca-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)