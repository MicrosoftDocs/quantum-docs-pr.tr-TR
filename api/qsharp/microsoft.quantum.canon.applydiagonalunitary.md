---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729626"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="c7512-102">ApplyDiagonalUnitary işlemi</span><span class="sxs-lookup"><span data-stu-id="c7512-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="c7512-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7512-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7512-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7512-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7512-105">Bir qubits kaydının sayısal tabanlı durumlarına bir karmaşık aşamalar dizisi uygular.</span><span class="sxs-lookup"><span data-stu-id="c7512-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="c7512-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c7512-106">Description</span></span>

<span data-ttu-id="c7512-107">Bu işlem, $n $-qubit numarası $ \ket{j} $ üzerinde ^ {i \ theta_j} $ $e karmaşık bir aşama uygulayan diyagonal bir Unitary uygular.</span><span class="sxs-lookup"><span data-stu-id="c7512-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="c7512-108">Özellikle, bu işlem Unitary tarafından temsil edilebilir</span><span class="sxs-lookup"><span data-stu-id="c7512-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="c7512-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="c7512-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="c7512-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="c7512-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c7512-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="c7512-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c7512-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c7512-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c7512-113">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="c7512-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="c7512-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="c7512-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="c7512-115">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c7512-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c7512-116">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c7512-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c7512-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7512-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c7512-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c7512-118">Remarks</span></span>

<span data-ttu-id="c7512-119">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="c7512-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="c7512-120">Referanslar</span><span class="sxs-lookup"><span data-stu-id="c7512-120">References</span></span>

- <span data-ttu-id="c7512-121">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="c7512-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="c7512-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c7512-122">See Also</span></span>

- [<span data-ttu-id="c7512-123">Microsoft. hisse. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="c7512-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)