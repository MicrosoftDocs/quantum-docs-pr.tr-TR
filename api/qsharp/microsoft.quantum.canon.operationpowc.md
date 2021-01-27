---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852346"
---
# <a name="operationpowc-function"></a><span data-ttu-id="c12f2-102">OperationPowC işlevi</span><span class="sxs-lookup"><span data-stu-id="c12f2-102">OperationPowC function</span></span>

<span data-ttu-id="c12f2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c12f2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c12f2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c12f2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c12f2-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="c12f2-105">Raises an operation to a power.</span></span>
<span data-ttu-id="c12f2-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="c12f2-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="c12f2-107">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="c12f2-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c12f2-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c12f2-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c12f2-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="c12f2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c12f2-110">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="c12f2-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="c12f2-111">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c12f2-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c12f2-112">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="c12f2-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="c12f2-113">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="c12f2-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c12f2-114">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="c12f2-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c12f2-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c12f2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c12f2-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c12f2-116">'T</span></span>

<span data-ttu-id="c12f2-117">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="c12f2-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="c12f2-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c12f2-118">See Also</span></span>

- [<span data-ttu-id="c12f2-119">Microsoft. hisse. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="c12f2-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)