---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients işlevi
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855853"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="c2096-102">StatePreparationPositiveCoefficients işlevi</span><span class="sxs-lookup"><span data-stu-id="c2096-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="c2096-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c2096-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c2096-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2096-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="c2096-105">StatePreparationPositiveCoefficients kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="c2096-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="c2096-106">Lütfen <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="c2096-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="c2096-107">Verilen hisse cıya durumunu hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="c2096-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="c2096-108">Döndürülen $U $ $-qubit hesaplama tabanlı durumu $ \ket{0...0} $ $n $ \ alpha_j \ge $0 pozitif katlarla rastgele bir hisse alma $ \ket{\psı} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="c2096-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="c2096-109">Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U \ket{0\cnoktalar 0} = \ket{\psı} = \frac{\ sum_ {j = 0 tarafından verilir} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="c2096-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="c2096-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="c2096-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c2096-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="c2096-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c2096-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c2096-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c2096-113">Dizi $2 ^ n $ katsayısı $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="c2096-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="c2096-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="c2096-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="c2096-115">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="c2096-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c2096-116">Bir durum hazırlama Unitary işlemi $U $.</span><span class="sxs-lookup"><span data-stu-id="c2096-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="c2096-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="c2096-117">Example</span></span>

<span data-ttu-id="c2096-118">Aşağıdaki kod parçacığı, qubit kaydındaki hisse durumu $ \ket{\psı} = \ sqrt {1/8} \ {0} Tus+ \ sqrt {7/8} \ {2} Tus$ ' i hazırlar `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="c2096-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="c2096-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c2096-119">Remarks</span></span>

<span data-ttu-id="c2096-120">Negatif giriş katsayıları $ \ alpha_j < $0, $ | \ alpha_j | $ değeri ile pozitif olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="c2096-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="c2096-121">`coefficients` $ \ alpha_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="c2096-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>