---
uid: Microsoft.Quantum.Canon.MultiplexZ
title: Çoğullexz işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits.
ms.openlocfilehash: dccfe86104263e23794bce33279e8748f11f5a54
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852437"
---
# <a name="multiplexz-operation"></a><span data-ttu-id="8d2ee-102">Çoğullexz işlemi</span><span class="sxs-lookup"><span data-stu-id="8d2ee-102">MultiplexZ operation</span></span>

<span data-ttu-id="8d2ee-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d2ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d2ee-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d2ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d2ee-105">Bir qubits dizisine bağlı bir Pauli Z dönüşü uygular.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-105">Applies a Pauli Z rotation conditioned on an array of qubits.</span></span>

```qsharp
operation MultiplexZ (coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="8d2ee-106">Description</span><span class="sxs-lookup"><span data-stu-id="8d2ee-106">Description</span></span>

<span data-ttu-id="8d2ee-107">Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $Z $ ile birlikte döndürmeler gerçekleştiren çarpma kontrollü Unitary işlemini uygular.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-107">This applies the multiply controlled unitary operation that performs rotations by angle $\theta_j$ about single-qubit Pauli operator $Z$ when controlled by the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="8d2ee-108">Özellikle, bu işlem Unitary tarafından temsil edilebilir</span><span class="sxs-lookup"><span data-stu-id="8d2ee-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="8d2ee-109">$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0} \ket{j}\bra{j} \otimes e^{i Z \theta_j}.</span></span>
<span data-ttu-id="8d2ee-110">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="8d2ee-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8d2ee-111">Giriş</span><span class="sxs-lookup"><span data-stu-id="8d2ee-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="8d2ee-112">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="8d2ee-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="8d2ee-113">Dizi $2 ^ n $ katsayısı $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="8d2ee-114">$J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="control--littleendian"></a><span data-ttu-id="8d2ee-115">Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8d2ee-115">control : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8d2ee-116">$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="8d2ee-117">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d2ee-117">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d2ee-118">$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-118">Single qubit register that is rotated by $e^{i P \theta_j}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d2ee-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d2ee-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d2ee-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8d2ee-120">Remarks</span></span>

<span data-ttu-id="8d2ee-121">`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="8d2ee-122">Başvurular</span><span class="sxs-lookup"><span data-stu-id="8d2ee-122">References</span></span>

- <span data-ttu-id="8d2ee-123">Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="8d2ee-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="8d2ee-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8d2ee-124">See Also</span></span>

- [<span data-ttu-id="8d2ee-125">Microsoft. hisse. Canon. yaklaşık Telteyıçoğullexz</span><span class="sxs-lookup"><span data-stu-id="8d2ee-125">Microsoft.Quantum.Canon.ApproximatelyMultiplexZ</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyMultiplexZ)