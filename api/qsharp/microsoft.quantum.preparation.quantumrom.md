---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Miktar Tumrom işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732623"
---
# <a name="quantumrom-function"></a><span data-ttu-id="a7f89-102">Miktar Tumrom işlevi</span><span class="sxs-lookup"><span data-stu-id="a7f89-102">QuantumROM function</span></span>

<span data-ttu-id="a7f89-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a7f89-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a7f89-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a7f89-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a7f89-105">, Belirli bir yoğunluk matrisini göstermek için hisse ROM tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="a7f89-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="a7f89-106">$N $ katsayısı $ \ alpha_j $ olan bir liste verildiğinde bu işlem, $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} için bir yaklaşık $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ değerini kullanan bir Unitary $U $ döndürür {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="a7f89-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="a7f89-107">Bu nedenle, $ \epsilon $ hatası $ | p_j-\frac{| alpha_j |} şeklindedir {\ sum_k | \ alpha_k |} | \le \ Epsilon/N $ ve $ \| \tilde\rho-\rho \| \le \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="a7f89-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="a7f89-108">Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} ^ {\lceil\ Log_2 N\rceıl} \ {0} Tus^ {k} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _j}.</span><span class="sxs-lookup"><span data-stu-id="a7f89-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="a7f89-109">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="a7f89-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="a7f89-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="a7f89-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a7f89-111">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a7f89-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a7f89-112">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="a7f89-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="a7f89-113">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a7f89-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a7f89-114">Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.</span><span class="sxs-lookup"><span data-stu-id="a7f89-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="a7f89-115">Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="a7f89-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="a7f89-116">Çıkış: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL)</span><span class="sxs-lookup"><span data-stu-id="a7f89-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="a7f89-117">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="a7f89-117">First parameter</span></span>

<span data-ttu-id="a7f89-118">`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.</span><span class="sxs-lookup"><span data-stu-id="a7f89-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="a7f89-119">İkinci parametre</span><span class="sxs-lookup"><span data-stu-id="a7f89-119">Second parameter</span></span>

<span data-ttu-id="a7f89-120">Katsayı dizisinin tek norm $ \ sum_j | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="a7f89-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="a7f89-121">Üçüncü parametre</span><span class="sxs-lookup"><span data-stu-id="a7f89-121">Third parameter</span></span>

<span data-ttu-id="a7f89-122">Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="a7f89-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="a7f89-123">Referanslar</span><span class="sxs-lookup"><span data-stu-id="a7f89-123">References</span></span>

- <span data-ttu-id="a7f89-124">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="a7f89-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>