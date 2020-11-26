---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateD
title: Yaklaşık Telypreparearbitrarna belirtilen işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 822efe08e66c43b7a3128d100e3e58a8c2ce3c2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193599"
---
# <a name="approximatelypreparearbitrarystated-operation"></a><span data-ttu-id="e3730-102">Yaklaşık Telypreparearbitrarna belirtilen işlem</span><span class="sxs-lookup"><span data-stu-id="e3730-102">ApproximatelyPrepareArbitraryStateD operation</span></span>

<span data-ttu-id="e3730-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e3730-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e3730-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3730-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3730-105">Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, verilen katsayıların belirli bir kabul toleransına göre tanımlanan bir durumu hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e3730-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateD (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e3730-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e3730-106">Description</span></span>

<span data-ttu-id="e3730-107">Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="e3730-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="e3730-108">Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetilir ve bu da tüm sıfırları durum üzerinde işlem yapar</span><span class="sxs-lookup"><span data-stu-id="e3730-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="e3730-109">$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="e3730-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="e3730-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="e3730-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e3730-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="e3730-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="e3730-112">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3730-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3730-113">Verilen durum hazırlanırken kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="e3730-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e3730-114">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e3730-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e3730-115">En fazla $2 ^ n $ gerçek katsayısıdır.</span><span class="sxs-lookup"><span data-stu-id="e3730-115">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="e3730-116">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="e3730-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="e3730-117">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e3730-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e3730-118">Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder.</span><span class="sxs-lookup"><span data-stu-id="e3730-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="e3730-119">Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.</span><span class="sxs-lookup"><span data-stu-id="e3730-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3730-120">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3730-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e3730-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e3730-121">Remarks</span></span>

<span data-ttu-id="e3730-122">_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="e3730-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="e3730-123">`coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="e3730-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="e3730-124">Başvurular</span><span class="sxs-lookup"><span data-stu-id="e3730-124">References</span></span>

- <span data-ttu-id="e3730-125">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="e3730-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>