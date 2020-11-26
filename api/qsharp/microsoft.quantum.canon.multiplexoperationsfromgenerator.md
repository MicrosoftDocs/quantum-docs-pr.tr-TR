---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Çoğullexoperationsfromgenerator işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 9fbbd9268d4a6b9f3d5fd203969f4bbeebe81b68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205958"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="c5530-102">Çoğullexoperationsfromgenerator işlemi</span><span class="sxs-lookup"><span data-stu-id="c5530-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="c5530-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5530-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5530-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5530-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5530-105">N-qubit numarası State $ \ket{j} $ tarafından denetlenen bir Unitary $V _j $ uygulayan çarpma özellikli Unitary işlemi uygular $U $.</span><span class="sxs-lookup"><span data-stu-id="c5530-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="c5530-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="c5530-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c5530-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="c5530-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="c5530-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 't => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL)</span><span class="sxs-lookup"><span data-stu-id="c5530-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="c5530-109">İlk öğenin `Int` $N $ ' nin sayısı ve ikinci öğe ise `(Int -> ('T => () is Adj + Ctl))` $ [0, N-1] $ içinde $j $ bir tamsayı alan ve _j $ $V Unitary işleminin çıkışını çıkaran bir demet.</span><span class="sxs-lookup"><span data-stu-id="c5530-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="c5530-110">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5530-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5530-111">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c5530-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="c5530-112">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="c5530-112">target : 'T</span></span>

<span data-ttu-id="c5530-113">Genel qubit kayıt, $V _j $ üzerinde çalışır.</span><span class="sxs-lookup"><span data-stu-id="c5530-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5530-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5530-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c5530-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c5530-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5530-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c5530-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c5530-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c5530-117">Remarks</span></span>

<span data-ttu-id="c5530-118">`coefficients` $2 ^ n $ değerinden azı belirtilmişse kimlik öğeleriyle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="c5530-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="c5530-119">Bu uygulama $n-$1 yardımcı qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="c5530-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="c5530-120">Başvurular</span><span class="sxs-lookup"><span data-stu-id="c5530-120">References</span></span>

- [<span data-ttu-id="c5530-121">*Andrew m. Childs, Dmitrı Maslov, Yunseong Nam, Neil J. No, Yuan su*, arxıv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="c5530-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)