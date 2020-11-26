---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateCP
title: Hazırlık Earbitraryıstatecp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 21a632c003da16fb5cb20ab97fc0d251a897892b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210650"
---
# <a name="preparearbitrarystatecp-operation"></a><span data-ttu-id="6b7d3-102">Hazırlık Earbitraryıstatecp işlemi</span><span class="sxs-lookup"><span data-stu-id="6b7d3-102">PrepareArbitraryStateCP operation</span></span>

<span data-ttu-id="6b7d3-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6b7d3-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6b7d3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b7d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b7d3-105">Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, söz konusu kayıt üzerinde verilen katsayıların açıklandığı bir durum hazırlar.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateCP (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="6b7d3-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6b7d3-106">Description</span></span>

<span data-ttu-id="6b7d3-107">Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="6b7d3-108">Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetilir ve bu da tüm sıfırları durum üzerinde işlem yapar</span><span class="sxs-lookup"><span data-stu-id="6b7d3-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="6b7d3-109">$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="6b7d3-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="6b7d3-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="6b7d3-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="6b7d3-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="6b7d3-112">katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="6b7d3-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="6b7d3-113">Mutlak değerleri ve aşama $ (r_j, t_j) ile temsil edilen en fazla $2 ^ n $ karmaşık katsayılar dizisi.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="6b7d3-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6b7d3-115">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6b7d3-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6b7d3-116">Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="6b7d3-117">Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b7d3-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b7d3-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6b7d3-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6b7d3-119">Remarks</span></span>

<span data-ttu-id="6b7d3-120">_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="6b7d3-121">`coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="6b7d3-122">Başvurular</span><span class="sxs-lookup"><span data-stu-id="6b7d3-122">References</span></span>

- <span data-ttu-id="6b7d3-123">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="6b7d3-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="6b7d3-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6b7d3-124">See Also</span></span>

- [<span data-ttu-id="6b7d3-125">Microsoft. hisse. hazırlık. yaklaşık Telypreparearbitrari durumu</span><span class="sxs-lookup"><span data-stu-id="6b7d3-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)