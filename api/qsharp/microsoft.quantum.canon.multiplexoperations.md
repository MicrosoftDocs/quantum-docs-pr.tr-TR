---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Çoğullexoperations işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728556"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="13e4c-102">Çoğullexoperations işlemi</span><span class="sxs-lookup"><span data-stu-id="13e4c-102">MultiplexOperations operation</span></span>

<span data-ttu-id="13e4c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="13e4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="13e4c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13e4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13e4c-105">Bir sayı dizisi tarafından denetlenen bir işlem dizisi uygular.</span><span class="sxs-lookup"><span data-stu-id="13e4c-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="13e4c-106">Diğer bir deyişle, $n $-qubit numarası $ \ket{j} $ tarafından denetlenen bir Unitary $V _j $ uygulayan çarpma özellikli Unitary işlemini uygular $U $.</span><span class="sxs-lookup"><span data-stu-id="13e4c-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="13e4c-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="13e4c-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="13e4c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="13e4c-108">Input</span></span>

### <a name="unitaries--t--unit-adj--ctl"></a><span data-ttu-id="13e4c-109">birimlere ait: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL []</span><span class="sxs-lookup"><span data-stu-id="13e4c-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="13e4c-110">En fazla $2 ^ n $ Unitary işlemi dizisi.</span><span class="sxs-lookup"><span data-stu-id="13e4c-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="13e4c-111">$J $ TH işlemi, küçük endian biçiminde bir $ \ket{j} $ kodlu sayı ile dizinlenir.</span><span class="sxs-lookup"><span data-stu-id="13e4c-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="13e4c-112">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="13e4c-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="13e4c-113">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="13e4c-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="13e4c-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="13e4c-114">target : 'T</span></span>

<span data-ttu-id="13e4c-115">Genel qubit kayıt, $V _j $ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="13e4c-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13e4c-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13e4c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="13e4c-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="13e4c-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13e4c-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="13e4c-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="13e4c-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="13e4c-119">Remarks</span></span>

<span data-ttu-id="13e4c-120">`coefficients` $2 ^ n $ değerinden azı belirtilmişse kimlik öğeleriyle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="13e4c-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="13e4c-121">Bu uygulama $n-$1 yardımcı qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="13e4c-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="13e4c-122">Referanslar</span><span class="sxs-lookup"><span data-stu-id="13e4c-122">References</span></span>

- <span data-ttu-id="13e4c-123">Hisse hızlı bir şekilde tüm hisse simülasyonu 'ne doğru bir şekilde. child. Chil, Dmitrı Maslov, Yunseong Nam, Neil J. No, Yuan su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="13e4c-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>