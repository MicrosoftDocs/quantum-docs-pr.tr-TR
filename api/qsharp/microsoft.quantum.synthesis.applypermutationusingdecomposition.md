---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Applyperdeğiştirici Tionusingayrıştırma işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733970"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="f9942-102">Applyperdeğiştirici Tionusingayrıştırma işlemi</span><span class="sxs-lookup"><span data-stu-id="f9942-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="f9942-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f9942-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f9942-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f9942-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f9942-105">Bir hisse cıklarca, ayrıştırma tabanlı senklerde bir PERMÜTASYONA göre rekabet eden bir değer sağlar.</span><span class="sxs-lookup"><span data-stu-id="f9942-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="f9942-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f9942-106">Description</span></span>

<span data-ttu-id="f9942-107">Bu yordam, ayrıştırma tabanlı sensıs yaklaşımını uygular.</span><span class="sxs-lookup"><span data-stu-id="f9942-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="f9942-108">Giriş, \{ \} bir $n $-değişken ters çevrilebilir Boole işlevini temsil eden, $2 ^ n $ öğe $0, \ noktalar, 2 ^ n-1 $ üzerinden bir permütasyon $ \pı $.</span><span class="sxs-lookup"><span data-stu-id="f9942-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="f9942-109">Algoritma yinelenen her bir dizin $i $ için aşağıdaki adımları gerçekleştirir:</span><span class="sxs-lookup"><span data-stu-id="f9942-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="f9942-110">İşlem $ ((\ pi_l, \ pi_r), \pı ') $, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin öğelerinde, $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bitleri değiştirmez ve öğelerinde bit $i $ değerini değiştirmeyin.</span><span class="sxs-lookup"><span data-stu-id="f9942-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="f9942-111">$ \Pı \leftarrow \pı ' $ değerini ayarlayın ve sabit noktalı olmayan öğelere bağlı olarak $ \ pi_l $ ve $ \ pi_r $ adresinden Truth tabloları türetirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f9942-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="f9942-112">Tüm değişken dizinleri için bu adımları uyguladıktan sonra, kalan permütasyon $ \pı $ kimlik olur ve toplanan Truth tablolarına ve dizinlerine göre, bir tane, işlemi kullanarak Truth tablo denetimli @"microsoft.quantum.intrinsic.x" işlemler uygulayabilir @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" .</span><span class="sxs-lookup"><span data-stu-id="f9942-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="f9942-113">Değişken sırası $0, \noktalar, n-$1 şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="f9942-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="f9942-114">İşlemde özel bir değişken sırası belirtilebilir @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="f9942-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="f9942-115">Giriş</span><span class="sxs-lookup"><span data-stu-id="f9942-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="f9942-116">izin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f9942-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f9942-117">0 ' dan başlayarak $2 ^ n $ öğe için bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="f9942-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f9942-118">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f9942-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f9942-119">Permütasyonun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="f9942-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9942-120">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9942-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="f9942-121">Referanslar</span><span class="sxs-lookup"><span data-stu-id="f9942-121">References</span></span>

- [<span data-ttu-id="f9942-122">*Alexde Vos* , *Yıvan Van Renterged* , ADV. comm. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="f9942-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="f9942-123">*Mathias Soeken* , *gamze Tag* , *Gerhard W. Dueck* , *Rolf Drechsler* , sembolik hesaplama 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="f9942-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="f9942-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f9942-124">See Also</span></span>

- [<span data-ttu-id="f9942-125">Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingdekompozisyontionwithvariableorder</span><span class="sxs-lookup"><span data-stu-id="f9942-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="f9942-126">Microsoft. hisse. Sensıs. Applyperdeğiştirici Tionusingtransformation</span><span class="sxs-lookup"><span data-stu-id="f9942-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)