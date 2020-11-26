---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193259"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="50d1d-102">StatePreparationPositiveCoefficients işlevi</span><span class="sxs-lookup"><span data-stu-id="50d1d-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="50d1d-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="50d1d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="50d1d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="50d1d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="50d1d-105">StatePreparationPositiveCoefficients kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="50d1d-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="50d1d-106">Lütfen <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="50d1d-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="50d1d-107">Verilen hisse cıya durumunu hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="50d1d-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="50d1d-108">Döndürülen $U $ $-qubit hesaplama tabanlı durumu $ \ket{0...0} $ $n $ \ alpha_j \ge $0 pozitif katlarla rastgele bir hisse alma $ \ket{\psı} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="50d1d-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="50d1d-109">Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U \ket{0\cnoktalar 0} = \ket{\psı} = \frac{\ sum_ {j = 0 tarafından verilir} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="50d1d-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="50d1d-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="50d1d-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="50d1d-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="50d1d-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="50d1d-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="50d1d-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="50d1d-113">Dizi $2 ^ n $ katsayısı $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="50d1d-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="50d1d-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="50d1d-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="50d1d-115">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="50d1d-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="50d1d-116">Bir durum hazırlama Unitary işlemi $U $.</span><span class="sxs-lookup"><span data-stu-id="50d1d-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="50d1d-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="50d1d-117">Remarks</span></span>

<span data-ttu-id="50d1d-118">Negatif giriş katsayıları $ \ alpha_j < $0, $ | \ alpha_j | $ değeri ile pozitif olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="50d1d-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="50d1d-119">`coefficients` $ \ alpha_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="50d1d-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>