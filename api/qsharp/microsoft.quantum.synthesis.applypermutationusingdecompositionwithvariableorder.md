---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733959"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="ec165-102">Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder işlemi</span><span class="sxs-lookup"><span data-stu-id="ec165-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="ec165-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ec165-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ec165-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec165-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec165-105">Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.</span><span class="sxs-lookup"><span data-stu-id="ec165-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="ec165-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ec165-106">Description</span></span>

<span data-ttu-id="ec165-107">Bu işlem, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" değişken sırasının belirtibileceği daha genel bir sürümdür.</span><span class="sxs-lookup"><span data-stu-id="ec165-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="ec165-108">Farklı bir değişken sırası, ayrıştırma dizisini ve kontrollü kapılar için kullanılan Truth tablolarını değiştirir @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="ec165-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="ec165-109">Bu nedenle, değişken sırasını değiştirmek, permütasyon sağlamak için kullanılan toplam kapı sayısını değiştirir.</span><span class="sxs-lookup"><span data-stu-id="ec165-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="ec165-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="ec165-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="ec165-111">izin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec165-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec165-112">0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="ec165-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="ec165-113">variableOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ec165-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ec165-114">0 ' dan başlayarak $n $ öğelerinden oluşan bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="ec165-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="ec165-115">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ec165-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ec165-116">Permütasyonun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="ec165-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec165-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec165-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ec165-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ec165-118">See Also</span></span>

- [<span data-ttu-id="ec165-119">Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingayrıştırma</span><span class="sxs-lookup"><span data-stu-id="ec165-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="ec165-120">Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingtransformation</span><span class="sxs-lookup"><span data-stu-id="ec165-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)