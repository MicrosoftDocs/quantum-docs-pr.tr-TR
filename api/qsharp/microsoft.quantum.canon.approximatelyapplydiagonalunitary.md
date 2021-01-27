---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5d8f6646c124f4296b9cd2abd71e73de5a530e55
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850346"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="06eeb-102">ApproximatelyApplyDiagonalUnitary işlemi</span><span class="sxs-lookup"><span data-stu-id="06eeb-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="06eeb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="06eeb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="06eeb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06eeb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06eeb-105">Bir qubit yazmacın sayısal temel durumlarına, belirli bir toleranstan göre küçük döndürme açılarını kesilmeye yönelik bir dizi karmaşık aşamalar uygular.</span><span class="sxs-lookup"><span data-stu-id="06eeb-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="06eeb-106">Description</span><span class="sxs-lookup"><span data-stu-id="06eeb-106">Description</span></span>

<span data-ttu-id="06eeb-107">Bu işlem, $n $-qubit numarası $ \ket{j} $ üzerinde ^ {i \ theta_j} $ $e karmaşık bir aşama uygulayan diyagonal bir Unitary uygular.</span><span class="sxs-lookup"><span data-stu-id="06eeb-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="06eeb-108">Özellikle, bu işlem Unitary tarafından temsil edilebilir</span><span class="sxs-lookup"><span data-stu-id="06eeb-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="06eeb-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="06eeb-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="06eeb-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="06eeb-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="06eeb-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="06eeb-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="06eeb-112">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06eeb-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06eeb-113">Küçük katsayıların kesilme toleransı.</span><span class="sxs-lookup"><span data-stu-id="06eeb-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="06eeb-114">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="06eeb-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="06eeb-115">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="06eeb-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="06eeb-116">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="06eeb-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="06eeb-117">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="06eeb-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="06eeb-118">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="06eeb-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="06eeb-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="06eeb-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="06eeb-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="06eeb-120">Remarks</span></span>

<span data-ttu-id="06eeb-121">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="06eeb-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="06eeb-122">Başvurular</span><span class="sxs-lookup"><span data-stu-id="06eeb-122">References</span></span>

- <span data-ttu-id="06eeb-123">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="06eeb-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="06eeb-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="06eeb-124">See Also</span></span>

- [<span data-ttu-id="06eeb-125">Microsoft. hisse. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="06eeb-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)