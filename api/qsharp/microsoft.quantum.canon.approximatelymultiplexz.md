---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Yaklaşık Telnalexz işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: b69b4de62241a7d16c2f07449115f864defda45d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841101"
---
# <a name="approximatelymultiplexz-operation"></a><span data-ttu-id="4a8e9-102">Yaklaşık Telnalexz işlemi</span><span class="sxs-lookup"><span data-stu-id="4a8e9-102">ApproximatelyMultiplexZ operation</span></span>

<span data-ttu-id="4a8e9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4a8e9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a8e9-105">Bir qubit dizisine bağlı bir Pauli Z dönüşü, belirli bir toleranstan göre küçük döndürme açılarını kesiluygular.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-105">Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4a8e9-106">Description</span><span class="sxs-lookup"><span data-stu-id="4a8e9-106">Description</span></span>

<span data-ttu-id="4a8e9-107">Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $Z $ ile birlikte döndürmeler gerçekleştiren çarpma kontrollü Unitary işlemini uygular.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="4a8e9-108">Özellikle, bu işlem Unitary tarafından temsil edilebilir</span><span class="sxs-lookup"><span data-stu-id="4a8e9-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="4a8e9-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="4a8e9-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="4a8e9-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="4a8e9-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="4a8e9-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="4a8e9-112">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4a8e9-113">Küçük katsayıların kesilme toleransı.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="4a8e9-114">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4a8e9-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4a8e9-115">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="4a8e9-116">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="4a8e9-117">Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4a8e9-118">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4a8e9-119">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4a8e9-120">$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a8e9-121">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a8e9-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a8e9-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4a8e9-122">Remarks</span></span>

<span data-ttu-id="4a8e9-123">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="4a8e9-124">Başvurular</span><span class="sxs-lookup"><span data-stu-id="4a8e9-124">References</span></span>

- <span data-ttu-id="4a8e9-125">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="4a8e9-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="4a8e9-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4a8e9-126">See Also</span></span>

- [<span data-ttu-id="4a8e9-127">Microsoft. hisse. Canon. MultiplexZ</span><span class="sxs-lookup"><span data-stu-id="4a8e9-127">Microsoft.Quantum.Canon.MultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.MultiplexZ)