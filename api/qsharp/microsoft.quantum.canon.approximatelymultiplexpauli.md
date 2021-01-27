---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Yaklaşık Telnalexpauli işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 1fc8a8857b6b37d4c3e812a3c4cb2941b9238800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844584"
---
# <a name="approximatelymultiplexpauli-operation"></a><span data-ttu-id="a58b6-102">Yaklaşık Telnalexpauli işlemi</span><span class="sxs-lookup"><span data-stu-id="a58b6-102">ApproximatelyMultiplexPauli operation</span></span>

<span data-ttu-id="a58b6-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a58b6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a58b6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a58b6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a58b6-105">Bir qubit dizisine bağlı bir Pauli dönüşü uygular, belirli bir toleransa göre küçük döndürme açılarını kesiliyor.</span><span class="sxs-lookup"><span data-stu-id="a58b6-105">Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a58b6-106">Description</span><span class="sxs-lookup"><span data-stu-id="a58b6-106">Description</span></span>

<span data-ttu-id="a58b6-107">Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $P $ ile birlikte döndürmeler gerçekleştiren bir çarpma kontrollü Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="a58b6-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="a58b6-108">Özellikle, bu işlemin eylemi Unitary tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="a58b6-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="a58b6-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="a58b6-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="a58b6-110">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="a58b6-110">\end{align}</span></span>

##

## <a name="input"></a><span data-ttu-id="a58b6-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="a58b6-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="a58b6-112">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a58b6-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a58b6-113">Küçük katsayıların kesilme toleransı.</span><span class="sxs-lookup"><span data-stu-id="a58b6-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a58b6-114">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a58b6-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a58b6-115">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="a58b6-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="a58b6-116">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="a58b6-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="a58b6-117">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a58b6-117">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a58b6-118">Pauli işleci $P $, döndürme eksenini belirler.</span><span class="sxs-lookup"><span data-stu-id="a58b6-118">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="a58b6-119">Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="a58b6-119">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="a58b6-120">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="a58b6-120">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a58b6-121">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a58b6-121">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a58b6-122">$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="a58b6-122">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a58b6-123">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a58b6-123">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a58b6-124">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a58b6-124">Remarks</span></span>

<span data-ttu-id="a58b6-125">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="a58b6-125">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="a58b6-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a58b6-126">See Also</span></span>

- [<span data-ttu-id="a58b6-127">Microsoft. hisse. Canon. MultiplexPauli</span><span class="sxs-lookup"><span data-stu-id="a58b6-127">Microsoft.Quantum.Canon.MultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.MultiplexPauli)