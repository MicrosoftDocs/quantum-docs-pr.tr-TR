---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 0a05b8a5891977a08ee2ae6a996657c6a8f3d792
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217127"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="9ff13-102">ApproximatelyApplyDiagonalUnitary işlemi</span><span class="sxs-lookup"><span data-stu-id="9ff13-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="9ff13-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ff13-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ff13-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ff13-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ff13-105">Bir qubit yazmacın sayısal temel durumlarına, belirli bir toleranstan göre küçük döndürme açılarını kesilmeye yönelik bir dizi karmaşık aşamalar uygular.</span><span class="sxs-lookup"><span data-stu-id="9ff13-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9ff13-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9ff13-106">Description</span></span>

<span data-ttu-id="9ff13-107">Bu işlem, $n $-qubit numarası $ \ket{j} $ üzerinde ^ {i \ theta_j} $ $e karmaşık bir aşama uygulayan diyagonal bir Unitary uygular.</span><span class="sxs-lookup"><span data-stu-id="9ff13-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="9ff13-108">Özellikle, bu işlem Unitary tarafından temsil edilebilir</span><span class="sxs-lookup"><span data-stu-id="9ff13-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="9ff13-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="9ff13-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="9ff13-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="9ff13-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="9ff13-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="9ff13-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="9ff13-112">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9ff13-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9ff13-113">Küçük katsayıların kesilme toleransı.</span><span class="sxs-lookup"><span data-stu-id="9ff13-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="9ff13-114">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9ff13-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9ff13-115">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="9ff13-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="9ff13-116">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="9ff13-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="9ff13-117">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9ff13-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9ff13-118">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="9ff13-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ff13-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ff13-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9ff13-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9ff13-120">Remarks</span></span>

<span data-ttu-id="9ff13-121">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="9ff13-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="9ff13-122">Başvurular</span><span class="sxs-lookup"><span data-stu-id="9ff13-122">References</span></span>

- <span data-ttu-id="9ff13-123">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="9ff13-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="9ff13-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ff13-124">See Also</span></span>

- [<span data-ttu-id="9ff13-125">Microsoft. hisse. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="9ff13-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)