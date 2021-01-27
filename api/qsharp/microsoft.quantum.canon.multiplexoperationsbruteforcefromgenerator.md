---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: Çoğullexoperationsbruteforcefromgenerator işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852515"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="d750d-102">Çoğullexoperationsbruteforcefromgenerator işlemi</span><span class="sxs-lookup"><span data-stu-id="d750d-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="d750d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d750d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d750d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d750d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d750d-105">N-qubit numarası State $ \ket{j} $ tarafından denetleniyorsa, bir Unitary $V _j $ uygulayan çarpma özellikli Unitary işlemini uygular $U $.</span><span class="sxs-lookup"><span data-stu-id="d750d-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="d750d-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="d750d-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d750d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="d750d-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="d750d-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 't => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL)</span><span class="sxs-lookup"><span data-stu-id="d750d-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="d750d-109">İlk öğenin `Int` $N $ ' nin sayısı ve ikinci öğe ise `(Int -> ('T => () is Adj + Ctl))` $ [0, N-1] $ içinde $j $ bir tamsayı alan ve _j $ $V Unitary işleminin çıkışını çıkaran bir demet.</span><span class="sxs-lookup"><span data-stu-id="d750d-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="d750d-110">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d750d-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d750d-111">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="d750d-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="d750d-112">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="d750d-112">target : 'T</span></span>

<span data-ttu-id="d750d-113">Genel qubit kayıt, $V _j $ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="d750d-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d750d-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d750d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d750d-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d750d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d750d-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d750d-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d750d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d750d-117">Remarks</span></span>

<span data-ttu-id="d750d-118">`coefficients` $2 ^ n $ değerinden azı belirtilmişse kimlik öğeleriyle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="d750d-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="d750d-119">Bu sürüm, n denetimli Unitary işleçleri aracılığıyla doğrudan döngülerle uygulanır.</span><span class="sxs-lookup"><span data-stu-id="d750d-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>