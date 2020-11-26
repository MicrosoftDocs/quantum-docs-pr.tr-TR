---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210378"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="d788d-102">StatePreparationComplexCoefficients işlevi</span><span class="sxs-lookup"><span data-stu-id="d788d-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="d788d-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d788d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d788d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d788d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="d788d-105">StatePreparationComplexCoefficients kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="d788d-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="d788d-106">Lütfen <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="d788d-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="d788d-107">Belirli bir hisse durumu hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="d788d-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="d788d-108">Döndürülen $U $, $n $-qubit hesaplama tabanlı durum $ \ket{0...0} $ t_j _j $r karmaşık katlara sahip, rastgele bir hisse</span><span class="sxs-lookup"><span data-stu-id="d788d-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="d788d-109">Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U\ket {0... tarafından verilir. 0} = \ket{\psı} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="d788d-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="d788d-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="d788d-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d788d-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="d788d-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="d788d-112">katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="d788d-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="d788d-113">Mutlak değerleri ve aşama $ (r_j, t_j) ile temsil edilen en fazla $2 ^ n $ karmaşık katsayılar dizisi.</span><span class="sxs-lookup"><span data-stu-id="d788d-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="d788d-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="d788d-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="d788d-115">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="d788d-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d788d-116">Bir durum hazırlama Unitary işlemi $U $.</span><span class="sxs-lookup"><span data-stu-id="d788d-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="d788d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d788d-117">Remarks</span></span>

<span data-ttu-id="d788d-118">_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="d788d-118">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="d788d-119">`coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.</span><span class="sxs-lookup"><span data-stu-id="d788d-119">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>