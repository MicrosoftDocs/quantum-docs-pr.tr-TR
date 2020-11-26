---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: Yaklaşık Telypreparearbitraryıstate işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193718"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="2ba8c-102">Yaklaşık Telypreparearbitraryıstate işlemi</span><span class="sxs-lookup"><span data-stu-id="2ba8c-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="2ba8c-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2ba8c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2ba8c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ba8c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="2ba8c-105">Yaklaşık Telypreparearbitraro kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="2ba8c-106">Lütfen <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="2ba8c-107">Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, verilen katsayıların belirli bir kabul toleransına göre tanımlanan bir durumu hazırlar.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2ba8c-108">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2ba8c-108">Description</span></span>

<span data-ttu-id="2ba8c-109">Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="2ba8c-110">Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetilir ve bu da tüm sıfırları durum üzerinde işlem yapar</span><span class="sxs-lookup"><span data-stu-id="2ba8c-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="2ba8c-111">$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="2ba8c-112">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="2ba8c-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="2ba8c-113">Giriş</span><span class="sxs-lookup"><span data-stu-id="2ba8c-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="2ba8c-114">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2ba8c-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2ba8c-115">Verilen durum hazırlanırken kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="2ba8c-116">katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="2ba8c-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="2ba8c-117">Mutlak değerleri ve aşama $ (r_j, t_j) ile temsil edilen en fazla $2 ^ n $ karmaşık katsayılar dizisi.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="2ba8c-118">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="2ba8c-119">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2ba8c-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2ba8c-120">Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="2ba8c-121">Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ba8c-122">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ba8c-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ba8c-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2ba8c-123">Remarks</span></span>

<span data-ttu-id="2ba8c-124">_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="2ba8c-125">`coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="2ba8c-126">Başvurular</span><span class="sxs-lookup"><span data-stu-id="2ba8c-126">References</span></span>

- <span data-ttu-id="2ba8c-127">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="2ba8c-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="2ba8c-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2ba8c-128">See Also</span></span>

- [<span data-ttu-id="2ba8c-129">Microsoft. hisse. hazırlık. yaklaşık Telypreparearbitrari durumu</span><span class="sxs-lookup"><span data-stu-id="2ba8c-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)