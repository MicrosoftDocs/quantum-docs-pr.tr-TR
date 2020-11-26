---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230030"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="29f41-102">PurifiedMixedState işlevi</span><span class="sxs-lookup"><span data-stu-id="29f41-102">PurifiedMixedState function</span></span>

<span data-ttu-id="29f41-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="29f41-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="29f41-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="29f41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="29f41-105">Belirli bir karma durumun bir listesini hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="29f41-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="29f41-106">"Yukarıda açıklanan karışık durum", | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ 'in {PI} katsayısının bir vektörü tarafından belirtilen durumlarını ifade eder.</span><span class="sxs-lookup"><span data-stu-id="29f41-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="29f41-107">Bu formun durumları, karışık durumlara azaltılabilir ρ ≔ Pi | ı ⟩ ⟨ ı | "çöp" kaydının (yani, hesaplama temelinde köşegen bir durum) üzerinde izleme yaparak.</span><span class="sxs-lookup"><span data-stu-id="29f41-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="29f41-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15Daha fazla tartışma için bkz..</span><span class="sxs-lookup"><span data-stu-id="29f41-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="29f41-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="29f41-109">Description</span></span>

<span data-ttu-id="29f41-110">, Söz konusu gösterimi bir durum hazırlama işlemi olarak döndüren belirli bir yoğunluk matrisini temsil etmek için hisse ROM tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="29f41-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="29f41-111">Özellikle, $N $ katsayıları $ \ alpha_j $ olan bir liste verildiğinde bu işlev bir yaklaşık $ $ \begin{hizalaması} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} hazırlamak için hisse \end{hizalaması} $ $ karma durumun $ $ \begin{hizalaması} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{hizalaması} $ $ her $p _j $, verilen katsayı $ \ alpha_j $ olan $ $ \begin{hizalaması} \left | şeklinde bir yaklaşık değer. p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} Her $j $ için \le \frac{\epsilon}{N} \end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="29f41-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="29f41-112">Başlangıçta $ \tus\ket{00\cnoktalar 0} durumunda bir dizin kaydı ve çöp qubits kaydı geçirildiğinde, {0} döndürülen işlem her iki kaydı da $ \tilde \rho $ ' ın ize hazırlar $ $ \begin{hizalaması} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{hizalaması} $ $, çöp yazmacı sıfırlama ve ayırmayı kaldırma, hedef hatası $ \epsilon $ içinde için istenen hazırlığı yapar.</span><span class="sxs-lookup"><span data-stu-id="29f41-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="29f41-113">Giriş</span><span class="sxs-lookup"><span data-stu-id="29f41-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="29f41-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="29f41-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="29f41-115">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="29f41-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="29f41-116">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="29f41-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="29f41-117">Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.</span><span class="sxs-lookup"><span data-stu-id="29f41-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="29f41-118">Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="29f41-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="29f41-119">Çıkış: [Mixedstatehazırlama](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="29f41-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="29f41-120">Birleşik bir dizin ve çöp kaydı üzerine bir birleşme olarak $ \tilde \rho $ hazırlayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="29f41-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="29f41-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="29f41-121">Remarks</span></span>

<span data-ttu-id="29f41-122">Bu işleme sunulan katsayılar, 1-norm sonrasında normalleştirilirler, bu nedenle katsayıların her zaman geçerli bir kategorik olasılık dağılımı tanımlayacak şekilde kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="29f41-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="29f41-123">Başvurular</span><span class="sxs-lookup"><span data-stu-id="29f41-123">References</span></span>

- <span data-ttu-id="29f41-124">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="29f41-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="29f41-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="29f41-125">See Also</span></span>

- [<span data-ttu-id="29f41-126">Microsoft. hisse. hazırlık. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="29f41-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)