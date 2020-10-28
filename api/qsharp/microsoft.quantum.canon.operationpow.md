---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728531"
---
# <a name="operationpow-function"></a><span data-ttu-id="44a34-102">OperationPow işlevi</span><span class="sxs-lookup"><span data-stu-id="44a34-102">OperationPow function</span></span>

<span data-ttu-id="44a34-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="44a34-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="44a34-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44a34-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44a34-105">Bir işlemi bir güce yükseltir.</span><span class="sxs-lookup"><span data-stu-id="44a34-105">Raises an operation to a power.</span></span>

<span data-ttu-id="44a34-106">Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="44a34-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="44a34-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="44a34-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="44a34-108">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44a34-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="44a34-109">Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.</span><span class="sxs-lookup"><span data-stu-id="44a34-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="44a34-110">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="44a34-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="44a34-111">$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.</span><span class="sxs-lookup"><span data-stu-id="44a34-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="44a34-112">Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="44a34-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="44a34-113">$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="44a34-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="44a34-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="44a34-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="44a34-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="44a34-115">'T</span></span>

<span data-ttu-id="44a34-116">Kapatılacak işlemin türü.</span><span class="sxs-lookup"><span data-stu-id="44a34-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="44a34-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="44a34-117">See Also</span></span>

- [<span data-ttu-id="44a34-118">Microsoft. hisse. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="44a34-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="44a34-119">Microsoft. hisse. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="44a34-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="44a34-120">Microsoft. hisse. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="44a34-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)