---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728489"
---
# <a name="operationpowca-function"></a><span data-ttu-id="69a52-102">OperationPowCA işlevi</span><span class="sxs-lookup"><span data-stu-id="69a52-102">OperationPowCA function</span></span>

<span data-ttu-id="69a52-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69a52-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69a52-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69a52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69a52-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="69a52-105">Raises an operation to a power.</span></span>
<span data-ttu-id="69a52-106">Değiştirici, `A` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="69a52-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="69a52-107">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="69a52-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="69a52-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="69a52-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="69a52-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="69a52-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="69a52-110">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="69a52-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="69a52-111">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69a52-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69a52-112">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="69a52-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="69a52-113">Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="69a52-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="69a52-114">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="69a52-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="69a52-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="69a52-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69a52-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="69a52-116">'T</span></span>

<span data-ttu-id="69a52-117">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="69a52-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="69a52-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="69a52-118">See Also</span></span>

- [<span data-ttu-id="69a52-119">Microsoft. hisse. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="69a52-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)