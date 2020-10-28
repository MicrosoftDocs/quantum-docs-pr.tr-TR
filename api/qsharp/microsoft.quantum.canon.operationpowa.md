---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728507"
---
# <a name="operationpowa-function"></a><span data-ttu-id="19d00-102">OperationPowA işlevi</span><span class="sxs-lookup"><span data-stu-id="19d00-102">OperationPowA function</span></span>

<span data-ttu-id="19d00-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="19d00-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="19d00-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19d00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19d00-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="19d00-105">Raises an operation to a power.</span></span>
<span data-ttu-id="19d00-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="19d00-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="19d00-107">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="19d00-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="19d00-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="19d00-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="19d00-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="19d00-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="19d00-110">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="19d00-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="19d00-111">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="19d00-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="19d00-112">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="19d00-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="19d00-113">Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="19d00-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="19d00-114">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="19d00-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="19d00-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="19d00-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="19d00-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="19d00-116">'T</span></span>

<span data-ttu-id="19d00-117">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="19d00-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="19d00-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="19d00-118">See Also</span></span>

- [<span data-ttu-id="19d00-119">Microsoft. hisse. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="19d00-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)