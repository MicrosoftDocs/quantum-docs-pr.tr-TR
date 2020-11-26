---
uid: Microsoft.Quantum.Canon.MultiplexPauli
title: Çoğullexpauli işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits.
ms.openlocfilehash: c29f7efa6b10835ce41ca4c535ec1371ac38ab63
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206043"
---
# <a name="multiplexpauli-operation"></a><span data-ttu-id="c42e4-102">Çoğullexpauli işlemi</span><span class="sxs-lookup"><span data-stu-id="c42e4-102">MultiplexPauli operation</span></span>

<span data-ttu-id="c42e4-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c42e4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c42e4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c42e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c42e4-105">Bir qubits dizisine bağlı bir Pauli dönüşü uygular.</span><span class="sxs-lookup"><span data-stu-id="c42e4-105">Applies a Pauli rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexPauli (coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c42e4-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c42e4-106">Description</span></span>

<span data-ttu-id="c42e4-107">Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $P $ ile birlikte döndürmeler gerçekleştiren bir çarpma kontrollü Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="c42e4-107">This applies a multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $P$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="c42e4-108">Özellikle, bu işlemin eylemi Unitary tarafından temsil edilir</span><span class="sxs-lookup"><span data-stu-id="c42e4-108">In particular, the action of this operation is represented by the unitary</span></span>

<span data-ttu-id="c42e4-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="c42e4-109">$$ \begin{align} U = \sum^{2^n - 1}_{j=0} \ket{j}\bra{j} \otimes e^{i P \theta_j}.</span></span>
<span data-ttu-id="c42e4-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="c42e4-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="c42e4-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="c42e4-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="c42e4-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c42e4-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c42e4-113">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="c42e4-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="c42e4-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="c42e4-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="pauli--pauli"></a><span data-ttu-id="c42e4-115">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="c42e4-115">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="c42e4-116">Pauli işleci $P $, döndürme eksenini belirler.</span><span class="sxs-lookup"><span data-stu-id="c42e4-116">Pauli operator $P$ that determines axis of rotation.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="c42e4-117">Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c42e4-117">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c42e4-118">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c42e4-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c42e4-119">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c42e4-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c42e4-120">$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="c42e4-120">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c42e4-121">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c42e4-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c42e4-122">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c42e4-122">Remarks</span></span>

<span data-ttu-id="c42e4-123">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="c42e4-123">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="see-also"></a><span data-ttu-id="c42e4-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c42e4-124">See Also</span></span>

- [<span data-ttu-id="c42e4-125">Microsoft. hisse. Canon. yaklaşık Telteyıçoğullexpauli</span><span class="sxs-lookup"><span data-stu-id="c42e4-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli)