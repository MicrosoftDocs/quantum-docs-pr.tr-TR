---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Applyperdeğiştirici Tionusingtransformation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858992"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="49b02-102">Applyperdeğiştirici Tionusingtransformation işlemi</span><span class="sxs-lookup"><span data-stu-id="49b02-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="49b02-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="49b02-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="49b02-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49b02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49b02-105">, Dönüştürme tabanlı senklik kullanarak bir PERMÜTASYONA, bir hisse cıklarca rekabet eden bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="49b02-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="49b02-106">Description</span><span class="sxs-lookup"><span data-stu-id="49b02-106">Description</span></span>

<span data-ttu-id="49b02-107">Bu yordam tek yönlü dönüştürme tabanlı sensıs yaklaşımını uygular.</span><span class="sxs-lookup"><span data-stu-id="49b02-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="49b02-108">Giriş, \{ \} $n $-değişken ters çevrilebilir Boole işlevini temsil eden, $2 ^ n $ öğe $0, \noktalar, 2 ^ n-1 $ üzerinden bir permütasyon $ \pı $.</span><span class="sxs-lookup"><span data-stu-id="49b02-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="49b02-109">Algoritma aşağıdaki adımları tekrarlayarak gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="49b02-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="49b02-110">$X \ne \pi (x) = y $ gibi en küçük $x $ bulun.</span><span class="sxs-lookup"><span data-stu-id="49b02-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="49b02-111">Çıkışlara uygulanan birden çok kontrollü Toffoli işlemlerini bul $ \pi (x) = x $ ve tüm $x ' < x $ $ $ $ $ $ $ $ $ $ $ $ $ $ olarak değiştirme</span><span class="sxs-lookup"><span data-stu-id="49b02-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="49b02-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="49b02-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="49b02-113">izin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="49b02-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="49b02-114">0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="49b02-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="49b02-115">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="49b02-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="49b02-116">Permütasyonun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="49b02-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49b02-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49b02-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="49b02-118">Örnek</span><span class="sxs-lookup"><span data-stu-id="49b02-118">Example</span></span>

<span data-ttu-id="49b02-119">Bir işlemi sentezleştirmek için `SWAP` :</span><span class="sxs-lookup"><span data-stu-id="49b02-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="49b02-120">Başvurular</span><span class="sxs-lookup"><span data-stu-id="49b02-120">References</span></span>

- [<span data-ttu-id="49b02-121">*D. Michael Miller*, *Dmitrı Maslov*, *Gerhard W. Dueck*, proc. dac 2003, ıeee, PP. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="49b02-121">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="49b02-122">*Mathias Soeken*, *Gerhard W. Dueck*, *D. MICHAEL Miller*, proc. RC 2016, sprçe, PP. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="49b02-122">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="49b02-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="49b02-123">See Also</span></span>

- [<span data-ttu-id="49b02-124">Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingayrıştırma</span><span class="sxs-lookup"><span data-stu-id="49b02-124">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)