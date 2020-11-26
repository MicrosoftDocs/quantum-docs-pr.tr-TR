---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Hazırlık Earbitrarna belirtilen işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: cca0ea16dca3f3da8ce76a43f1012ffa0e4a72e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210616"
---
# <a name="preparearbitrarystated-operation"></a><span data-ttu-id="e2181-102">Hazırlık Earbitrarna belirtilen işlem</span><span class="sxs-lookup"><span data-stu-id="e2181-102">PrepareArbitraryStateD operation</span></span>

<span data-ttu-id="e2181-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e2181-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e2181-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2181-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2181-105">Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, söz konusu kayıt üzerinde verilen katsayıların açıklandığı bir durum hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e2181-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e2181-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e2181-106">Description</span></span>

<span data-ttu-id="e2181-107">Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e2181-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="e2181-108">Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetimi yapılabilir ve bu durum,</span><span class="sxs-lookup"><span data-stu-id="e2181-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ that acts on the all-zeros state as</span></span>

<span data-ttu-id="e2181-109">$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="e2181-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="e2181-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="e2181-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e2181-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="e2181-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="e2181-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e2181-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e2181-113">En fazla $2 ^ n $ gerçek katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="e2181-113">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="e2181-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="e2181-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e2181-115">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e2181-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e2181-116">Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder.</span><span class="sxs-lookup"><span data-stu-id="e2181-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="e2181-117">Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.</span><span class="sxs-lookup"><span data-stu-id="e2181-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2181-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2181-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e2181-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e2181-119">Remarks</span></span>

<span data-ttu-id="e2181-120">_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="e2181-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="e2181-121">`coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="e2181-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e2181-122">Başvurular</span><span class="sxs-lookup"><span data-stu-id="e2181-122">References</span></span>

- <span data-ttu-id="e2181-123">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e2181-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="e2181-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e2181-124">See Also</span></span>

- [<span data-ttu-id="e2181-125">Microsoft. hisse. hazırlık. yaklaşık Telypreparearbitrari durumu</span><span class="sxs-lookup"><span data-stu-id="e2181-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)