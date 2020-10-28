---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728495"
---
# <a name="operationpowc-function"></a><span data-ttu-id="ede2a-102">OperationPowC işlevi</span><span class="sxs-lookup"><span data-stu-id="ede2a-102">OperationPowC function</span></span>

<span data-ttu-id="ede2a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ede2a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ede2a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ede2a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ede2a-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="ede2a-105">Raises an operation to a power.</span></span>
<span data-ttu-id="ede2a-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="ede2a-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="ede2a-107">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="ede2a-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ede2a-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ede2a-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="ede2a-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ede2a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ede2a-110">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="ede2a-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="ede2a-111">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ede2a-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ede2a-112">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="ede2a-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="ede2a-113">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="ede2a-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="ede2a-114">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="ede2a-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ede2a-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ede2a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ede2a-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ede2a-116">'T</span></span>

<span data-ttu-id="ede2a-117">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="ede2a-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="ede2a-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ede2a-118">See Also</span></span>

- [<span data-ttu-id="ede2a-119">Microsoft. hisse. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="ede2a-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)