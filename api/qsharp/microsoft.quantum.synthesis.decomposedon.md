---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855522"
---
# <a name="decomposedon-function"></a><span data-ttu-id="3c2c0-102">DecomposedOn işlevi</span><span class="sxs-lookup"><span data-stu-id="3c2c0-102">DecomposedOn function</span></span>

<span data-ttu-id="3c2c0-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="3c2c0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c2c0-105">Bir değişken üzerinde bir permütasyon 'yi kaldırır</span><span class="sxs-lookup"><span data-stu-id="3c2c0-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="3c2c0-106">Description</span><span class="sxs-lookup"><span data-stu-id="3c2c0-106">Description</span></span>

<span data-ttu-id="3c2c0-107">Bir permütasyon $ \pı $ ( `perm` ) ve bir dizin $i $ () verildiğinde `index` , bu yöntem, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bit değiştirmelerini sağlayan üç permütasyon $ ((\ pi_l, \ pi_r), \pı ') $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="3c2c0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="3c2c0-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="3c2c0-109">izin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c2c0-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="3c2c0-110">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="3c2c0-111">Çıkış: (([Int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="3c2c0-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>



## <a name="example"></a><span data-ttu-id="3c2c0-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="3c2c0-112">Example</span></span>

<span data-ttu-id="3c2c0-113">Girişin izin = [0, 2, 3, 5, 7, 1, 4, 6] ve index = 0 olduğunu varsayalım, bu işlev aşağıdaki tabloya bağlı üç permütasyon hesaplar ve bu durumda, Grup `perm` a 'daki ve Grup D 'deki öğelerle birlikte ikili gösterimde olan permütasyonu listeleyin.  Sütunlarda bit dizinleri listelenir.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-113">Assume that the input is perm = [0, 2, 3, 5, 7, 1, 4, 6] and index = 0, then this function computes three permutations based on the following table, which lists the permutation `perm` in binary notation with elements in group A and images in group D.  The columns list the bit indices.</span></span>

<span data-ttu-id="3c2c0-114">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="3c2c0-114">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="3c2c0-115">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-115">2 1 0</span></span> | <span data-ttu-id="3c2c0-116">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-116">2 1 0</span></span> | <span data-ttu-id="3c2c0-117">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-117">2 1 0</span></span> | <span data-ttu-id="3c2c0-118">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-118">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="3c2c0-119">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-119">0 0 0</span></span> |       |       | <span data-ttu-id="3c2c0-120">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-120">0 0 0</span></span> | <span data-ttu-id="3c2c0-121">0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-121">0</span></span>
| <span data-ttu-id="3c2c0-122">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-122">0 0 1</span></span> |       |       | <span data-ttu-id="3c2c0-123">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-123">0 1 0</span></span> | <span data-ttu-id="3c2c0-124">2</span><span class="sxs-lookup"><span data-stu-id="3c2c0-124">2</span></span>
| <span data-ttu-id="3c2c0-125">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-125">0 1 0</span></span> |       |       | <span data-ttu-id="3c2c0-126">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-126">0 1 1</span></span> | <span data-ttu-id="3c2c0-127">3</span><span class="sxs-lookup"><span data-stu-id="3c2c0-127">3</span></span>
| <span data-ttu-id="3c2c0-128">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-128">0 1 1</span></span> |       |       | <span data-ttu-id="3c2c0-129">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-129">1 0 1</span></span> | <span data-ttu-id="3c2c0-130">5</span><span class="sxs-lookup"><span data-stu-id="3c2c0-130">5</span></span>
| <span data-ttu-id="3c2c0-131">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-131">1 0 0</span></span> |       |       | <span data-ttu-id="3c2c0-132">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-132">1 1 1</span></span> | <span data-ttu-id="3c2c0-133">7</span><span class="sxs-lookup"><span data-stu-id="3c2c0-133">7</span></span>
| <span data-ttu-id="3c2c0-134">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-134">1 0 1</span></span> |       |       | <span data-ttu-id="3c2c0-135">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-135">0 0 1</span></span> | <span data-ttu-id="3c2c0-136">1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-136">1</span></span>
| <span data-ttu-id="3c2c0-137">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-137">1 1 0</span></span> |       |       | <span data-ttu-id="3c2c0-138">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-138">1 0 0</span></span> | <span data-ttu-id="3c2c0-139">4</span><span class="sxs-lookup"><span data-stu-id="3c2c0-139">4</span></span>
| <span data-ttu-id="3c2c0-140">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-140">1 1 1</span></span> |       |       | <span data-ttu-id="3c2c0-141">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-141">1 1 0</span></span> | <span data-ttu-id="3c2c0-142">6</span><span class="sxs-lookup"><span data-stu-id="3c2c0-142">6</span></span>

<span data-ttu-id="3c2c0-143">0 ' A eşit olmayan dizinler için tüm değerler (= Dizin), A 'dan B 'ye ve D 'den C 'ye kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-143">All values for indices not equal to 0 (= index) are copied from A to B and from D to C.</span></span>

<span data-ttu-id="3c2c0-144">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="3c2c0-144">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="3c2c0-145">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-145">2 1 0</span></span> | <span data-ttu-id="3c2c0-146">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-146">2 1 0</span></span> | <span data-ttu-id="3c2c0-147">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-147">2 1 0</span></span> | <span data-ttu-id="3c2c0-148">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-148">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="3c2c0-149">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-149">0 0 0</span></span> | <span data-ttu-id="3c2c0-150">0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-150">0 0</span></span>   | <span data-ttu-id="3c2c0-151">0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-151">0 0</span></span>   | <span data-ttu-id="3c2c0-152">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-152">0 0 0</span></span> |
| <span data-ttu-id="3c2c0-153">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-153">0 0 1</span></span> | <span data-ttu-id="3c2c0-154">0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-154">0 0</span></span>   | <span data-ttu-id="3c2c0-155">0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-155">0 1</span></span>   | <span data-ttu-id="3c2c0-156">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-156">0 1 0</span></span> |
| <span data-ttu-id="3c2c0-157">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-157">0 1 0</span></span> | <span data-ttu-id="3c2c0-158">0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-158">0 1</span></span>   | <span data-ttu-id="3c2c0-159">0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-159">0 1</span></span>   | <span data-ttu-id="3c2c0-160">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-160">0 1 1</span></span> |
| <span data-ttu-id="3c2c0-161">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-161">0 1 1</span></span> | <span data-ttu-id="3c2c0-162">0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-162">0 1</span></span>   | <span data-ttu-id="3c2c0-163">1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-163">1 0</span></span>   | <span data-ttu-id="3c2c0-164">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-164">1 0 1</span></span> |
| <span data-ttu-id="3c2c0-165">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-165">1 0 0</span></span> | <span data-ttu-id="3c2c0-166">1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-166">1 0</span></span>   | <span data-ttu-id="3c2c0-167">1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-167">1 1</span></span>   | <span data-ttu-id="3c2c0-168">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-168">1 1 1</span></span> |
| <span data-ttu-id="3c2c0-169">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-169">1 0 1</span></span> | <span data-ttu-id="3c2c0-170">1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-170">1 0</span></span>   | <span data-ttu-id="3c2c0-171">0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-171">0 0</span></span>   | <span data-ttu-id="3c2c0-172">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-172">0 0 1</span></span> |
| <span data-ttu-id="3c2c0-173">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-173">1 1 0</span></span> | <span data-ttu-id="3c2c0-174">1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-174">1 1</span></span>   | <span data-ttu-id="3c2c0-175">1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-175">1 0</span></span>   | <span data-ttu-id="3c2c0-176">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-176">1 0 0</span></span> |
| <span data-ttu-id="3c2c0-177">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-177">1 1 1</span></span> | <span data-ttu-id="3c2c0-178">1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-178">1 1</span></span>   | <span data-ttu-id="3c2c0-179">1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-179">1 1</span></span>   | <span data-ttu-id="3c2c0-180">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-180">1 1 0</span></span> |

<span data-ttu-id="3c2c0-181">Sonraki bir 0, blok B 'deki 0 sütununda boş bir dizine sahip ilk öğe için konur ve ardından önek eşleşen bir 1 B 'ye yerleştirilir (ilk durumda, 0 0 olan diğer satırda).</span><span class="sxs-lookup"><span data-stu-id="3c2c0-181">Next a 0 is placed for the first element with an empty index at column 0 in block B and then a 1 is placed in B where the prefix matches (in the first case the other row with indices 0 0).</span></span>
<span data-ttu-id="3c2c0-182">Daha sonra, bir 1 blok C içindeki aynı satıra ve blok C içindeki karşılık gelen önek için 0 ' a eklenir.  Bu işlem, tüm dizinler B ve C bloklarına 0 sütununa yerleştirilene kadar yinelenir.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-182">Afterwards, a 1 is added in the same row in block C, and then a 0 for the corresponding prefix in block C.  This process is repeated, until all indices have been placed in column 0 in blocks B and C.</span></span>

<span data-ttu-id="3c2c0-183">|   A |   B |   C |   D |</span><span class="sxs-lookup"><span data-stu-id="3c2c0-183">|   A   |   B   |   C   |   D   |</span></span>
| <span data-ttu-id="3c2c0-184">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-184">2 1 0</span></span> | <span data-ttu-id="3c2c0-185">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-185">2 1 0</span></span> | <span data-ttu-id="3c2c0-186">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-186">2 1 0</span></span> | <span data-ttu-id="3c2c0-187">2 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-187">2 1 0</span></span> |
|-------|-------|-------|-------|
| <span data-ttu-id="3c2c0-188">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-188">0 0 0</span></span> | <span data-ttu-id="3c2c0-189">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-189">0 0 0</span></span> | <span data-ttu-id="3c2c0-190">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-190">0 0 0</span></span> | <span data-ttu-id="3c2c0-191">0 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-191">0 0 0</span></span> |
| <span data-ttu-id="3c2c0-192">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-192">0 0 1</span></span> | <span data-ttu-id="3c2c0-193">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-193">0 0 1</span></span> | <span data-ttu-id="3c2c0-194">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-194">0 1 1</span></span> | <span data-ttu-id="3c2c0-195">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-195">0 1 0</span></span> |
| <span data-ttu-id="3c2c0-196">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-196">0 1 0</span></span> | <span data-ttu-id="3c2c0-197">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-197">0 1 0</span></span> | <span data-ttu-id="3c2c0-198">0 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-198">0 1 0</span></span> | <span data-ttu-id="3c2c0-199">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-199">0 1 1</span></span> |
| <span data-ttu-id="3c2c0-200">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-200">0 1 1</span></span> | <span data-ttu-id="3c2c0-201">0 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-201">0 1 1</span></span> | <span data-ttu-id="3c2c0-202">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-202">1 0 1</span></span> | <span data-ttu-id="3c2c0-203">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-203">1 0 1</span></span> |
| <span data-ttu-id="3c2c0-204">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-204">1 0 0</span></span> | <span data-ttu-id="3c2c0-205">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-205">1 0 0</span></span> | <span data-ttu-id="3c2c0-206">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-206">1 1 0</span></span> | <span data-ttu-id="3c2c0-207">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-207">1 1 1</span></span> |
| <span data-ttu-id="3c2c0-208">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-208">1 0 1</span></span> | <span data-ttu-id="3c2c0-209">1 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-209">1 0 1</span></span> | <span data-ttu-id="3c2c0-210">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-210">0 0 1</span></span> | <span data-ttu-id="3c2c0-211">0 0 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-211">0 0 1</span></span> |
| <span data-ttu-id="3c2c0-212">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-212">1 1 0</span></span> | <span data-ttu-id="3c2c0-213">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-213">1 1 0</span></span> | <span data-ttu-id="3c2c0-214">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-214">1 0 0</span></span> | <span data-ttu-id="3c2c0-215">1 0 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-215">1 0 0</span></span> |
| <span data-ttu-id="3c2c0-216">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-216">1 1 1</span></span> | <span data-ttu-id="3c2c0-217">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-217">1 1 1</span></span> | <span data-ttu-id="3c2c0-218">1 1 1</span><span class="sxs-lookup"><span data-stu-id="3c2c0-218">1 1 1</span></span> | <span data-ttu-id="3c2c0-219">1 1 0</span><span class="sxs-lookup"><span data-stu-id="3c2c0-219">1 1 0</span></span> |

<span data-ttu-id="3c2c0-220">Tablodan üç yeni permütasyon okuyabiliriz:</span><span class="sxs-lookup"><span data-stu-id="3c2c0-220">We can read three new permutations from the table:</span></span>

- <span data-ttu-id="3c2c0-221">$ \ pi_l $, A içindeki öğeler, B 'deki görüntüler (sol)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-221">$\pi_l$ with elements in A, images in B (left)</span></span>
- <span data-ttu-id="3c2c0-222">C içindeki öğelerle $ \ pi_r $, C 'deki görüntüler (sağ)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-222">$\pi_r$ with elements in D, images in C (right)</span></span>
- <span data-ttu-id="3c2c0-223">$ \pi ' $ B 'deki öğelerle, C 'deki görüntüler (geri kalan)</span><span class="sxs-lookup"><span data-stu-id="3c2c0-223">$\pi'$  with elements in B, images in C (remainder)</span></span>

<span data-ttu-id="3c2c0-224">Tasarım bit değerleri, 1 ve 2. dizinler için $ \ pi_l $ ve $ \ pi_r $ içinde değişmez ve 0 dizini için $ \ pi_ ' $ içinde için bit değerleri değişmez.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-224">Note that by design bit values do not change in $\pi_l$ and $\pi_r$ for indices 1 and 2, and bit values do not change for in $\pi_'$ for index 0.</span></span>  <span data-ttu-id="3c2c0-225">Ayrıca $ \ pi_l $ ve $ \ pi_r $ öğesinin kendinden ters olması gerektiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3c2c0-225">Also note that $\pi_l$ and $\pi_r$ must be self-inverse.</span></span>

<span data-ttu-id="3c2c0-226">Türetilmiş ve döndürülen permütasyon: Left = [0, 1, 2, 3, 4, 5, 6, 7] Right = [0, 1, 3, 2, 4, 5, 7, 6] kalanı = [0, 3, 2, 5, 6, 1, 4, 7]</span><span class="sxs-lookup"><span data-stu-id="3c2c0-226">The derived and returned permutations are: left      = [0, 1, 2, 3, 4, 5, 6, 7] right     = [0, 1, 3, 2, 4, 5, 7, 6] remainder = [0, 3, 2, 5, 6, 1, 4, 7]</span></span>