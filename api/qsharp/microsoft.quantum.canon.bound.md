---
uid: Microsoft.Quantum.Canon.Bound
title: Bağlantılı işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728928"
---
# <a name="bound-function"></a><span data-ttu-id="bc896-102">Bağlantılı işlev</span><span class="sxs-lookup"><span data-stu-id="bc896-102">Bound function</span></span>

<span data-ttu-id="bc896-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc896-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc896-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc896-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc896-105">Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bc896-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="bc896-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="bc896-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="bc896-107">işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="bc896-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="bc896-108">Belirli bir girişte gerçekleştirilecek işlemler dizisi.</span><span class="sxs-lookup"><span data-stu-id="bc896-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="bc896-109">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc896-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bc896-110">Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="bc896-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bc896-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bc896-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc896-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bc896-112">'T</span></span>

<span data-ttu-id="bc896-113">Dizideki her bir işlemin üzerinde işlem gören hedef.</span><span class="sxs-lookup"><span data-stu-id="bc896-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc896-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bc896-114">See Also</span></span>

- [<span data-ttu-id="bc896-115">Microsoft. hisse. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="bc896-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="bc896-116">Microsoft. hisse. Canon. sını</span><span class="sxs-lookup"><span data-stu-id="bc896-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="bc896-117">Microsoft. hisse. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="bc896-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)