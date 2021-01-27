---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854300"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="ada7e-102">PurifiedMixedState işlevi</span><span class="sxs-lookup"><span data-stu-id="ada7e-102">PurifiedMixedState function</span></span>

<span data-ttu-id="ada7e-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="ada7e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="ada7e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ada7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ada7e-105">Belirli bir karma durumun bir listesini hazırlayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="ada7e-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="ada7e-106">"Yukarıda açıklanan karışık durum", | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ 'in {PI} katsayısının bir vektörü tarafından belirtilen durumlarını ifade eder.</span><span class="sxs-lookup"><span data-stu-id="ada7e-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="ada7e-107">Bu formun durumları, karışık durumlara azaltılabilir ρ ≔ Pi | ı ⟩ ⟨ ı | "çöp" kaydının (yani, hesaplama temelinde köşegen bir durum) üzerinde izleme yaparak.</span><span class="sxs-lookup"><span data-stu-id="ada7e-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="ada7e-108"> https://arxiv.org/pdf/1805.03662.pdf?page=15Daha fazla tartışma için bkz..</span><span class="sxs-lookup"><span data-stu-id="ada7e-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="ada7e-109">Description</span><span class="sxs-lookup"><span data-stu-id="ada7e-109">Description</span></span>

<span data-ttu-id="ada7e-110">, Söz konusu gösterimi bir durum hazırlama işlemi olarak döndüren belirli bir yoğunluk matrisini temsil etmek için hisse ROM tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="ada7e-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="ada7e-111">Özellikle, $N $ katsayıları $ \ alpha_j $ olan bir liste verildiğinde bu işlev bir yaklaşık $ $ \begin{hizalaması} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} hazırlamak için hisse \end{hizalaması} $ $ karma durumun $ $ \begin{hizalaması} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{hizalaması} $ $ her $p _j $, verilen katsayı $ \ alpha_j $ olan $ $ \begin{hizalaması} \left | şeklinde bir yaklaşık değer. p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} Her $j $ için \le \frac{\epsilon}{N} \end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="ada7e-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="ada7e-112">Başlangıçta $ \tus\ket{00\cnoktalar 0} durumunda bir dizin kaydı ve çöp qubits kaydı geçirildiğinde, {0} döndürülen işlem her iki kaydı da $ \tilde \rho $ ' ın ize hazırlar $ $ \begin{hizalaması} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{hizalaması} $ $, çöp yazmacı sıfırlama ve ayırmayı kaldırma, hedef hatası $ \epsilon $ içinde için istenen hazırlığı yapar.</span><span class="sxs-lookup"><span data-stu-id="ada7e-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="ada7e-113">Giriş</span><span class="sxs-lookup"><span data-stu-id="ada7e-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="ada7e-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ada7e-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ada7e-115">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="ada7e-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="ada7e-116">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ada7e-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ada7e-117">Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.</span><span class="sxs-lookup"><span data-stu-id="ada7e-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="ada7e-118">Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="ada7e-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="ada7e-119">Çıkış: [Mixedstatehazırlama](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="ada7e-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="ada7e-120">Birleşik bir dizin ve çöp kaydı üzerine bir birleşme olarak $ \tilde \rho $ hazırlayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="ada7e-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="ada7e-121">Örnek</span><span class="sxs-lookup"><span data-stu-id="ada7e-121">Example</span></span>

<span data-ttu-id="ada7e-122">Aşağıdaki kod parçacığı $3 $-qubit durumu $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} için bir yol hazırlar {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, burada $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $ ve hedef hata, $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="ada7e-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="ada7e-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ada7e-123">Remarks</span></span>

<span data-ttu-id="ada7e-124">Bu işleme sunulan katsayılar, 1-norm sonrasında normalleştirilirler, bu nedenle katsayıların her zaman geçerli bir kategorik olasılık dağılımı tanımlayacak şekilde kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="ada7e-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="ada7e-125">Başvurular</span><span class="sxs-lookup"><span data-stu-id="ada7e-125">References</span></span>

- <span data-ttu-id="ada7e-126">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="ada7e-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="ada7e-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ada7e-127">See Also</span></span>

- [<span data-ttu-id="ada7e-128">Microsoft. hisse. hazırlık. PurifiedMixedStateWithData</span><span class="sxs-lookup"><span data-stu-id="ada7e-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)