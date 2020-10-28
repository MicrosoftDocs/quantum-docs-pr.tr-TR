---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732586"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="09631-102">StatePreparationPositiveCoefficients işlevi</span><span class="sxs-lookup"><span data-stu-id="09631-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="09631-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="09631-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="09631-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09631-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09631-105">Verilen hisse cıya durumunu hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="09631-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="09631-106">Döndürülen $U $ $-qubit hesaplama tabanlı durumu $ \ket{0...0} $ $n $ \ alpha_j \ge $0 pozitif katlarla rastgele bir hisse alma $ \ket{\psı} $ hazırlar.</span><span class="sxs-lookup"><span data-stu-id="09631-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="09631-107">Yeni ayrılmış bir kayıttaki U eylemi $ $ \begin{hizalaması} U \ket{0\cnoktalar 0} = \ket{\psı} = \frac{\ sum_ {j = 0 tarafından verilir} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="09631-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="09631-108">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="09631-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="09631-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="09631-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="09631-110">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="09631-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="09631-111">Dizi $2 ^ n $ katsayısı $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="09631-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="09631-112">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="09631-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="09631-113">Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL</span><span class="sxs-lookup"><span data-stu-id="09631-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="09631-114">Bir durum hazırlama Unitary işlemi $U $.</span><span class="sxs-lookup"><span data-stu-id="09631-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="09631-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="09631-115">Remarks</span></span>

<span data-ttu-id="09631-116">Negatif giriş katsayıları $ \ alpha_j < $0, $ | \ alpha_j | $ değeri ile pozitif olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="09631-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="09631-117">`coefficients` $ \ alpha_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="09631-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>