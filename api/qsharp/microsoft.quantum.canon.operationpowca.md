---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 338c40f8eb9d6f1782989f2a91c86df561d480bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852318"
---
# <a name="operationpowca-function"></a><span data-ttu-id="e4fcf-102">OperationPowCA işlevi</span><span class="sxs-lookup"><span data-stu-id="e4fcf-102">OperationPowCA function</span></span>

<span data-ttu-id="e4fcf-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4fcf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4fcf-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4fcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4fcf-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-105">Raises an operation to a power.</span></span>
<span data-ttu-id="e4fcf-106">Değiştirici, `A` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="e4fcf-107">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="e4fcf-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="e4fcf-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="e4fcf-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e4fcf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e4fcf-110">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="e4fcf-111">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4fcf-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4fcf-112">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="e4fcf-113">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e4fcf-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e4fcf-114">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e4fcf-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e4fcf-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e4fcf-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e4fcf-116">'T</span></span>

<span data-ttu-id="e4fcf-117">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4fcf-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e4fcf-118">See Also</span></span>

- [<span data-ttu-id="e4fcf-119">Microsoft. hisse. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="e4fcf-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)