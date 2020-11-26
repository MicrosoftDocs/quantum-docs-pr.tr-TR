---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Miktar Tumrom işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229894"
---
# <a name="quantumrom-function"></a><span data-ttu-id="01a0f-102">Miktar Tumrom işlevi</span><span class="sxs-lookup"><span data-stu-id="01a0f-102">QuantumROM function</span></span>

<span data-ttu-id="01a0f-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="01a0f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="01a0f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01a0f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="01a0f-105">Miktarı kullanım dışı bırakıldı.</span><span class="sxs-lookup"><span data-stu-id="01a0f-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="01a0f-106">Lütfen <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> bunun yerine kullanın.</span><span class="sxs-lookup"><span data-stu-id="01a0f-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="01a0f-107">, Belirli bir yoğunluk matrisini göstermek için hisse ROM tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="01a0f-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="01a0f-108">$N $ katsayısı $ \ alpha_j $ olan bir liste verildiğinde bu işlem, $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} için bir yaklaşık $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ değerini kullanan bir Unitary $U $ döndürür {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="01a0f-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="01a0f-109">Bu nedenle, $ \epsilon $ hatası $ | p_j-\frac{| alpha_j |} şeklindedir {\ sum_k | \ alpha_k |} | \le \ Epsilon/N $ ve $ \| \tilde\rho-\rho \| \le \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="01a0f-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="01a0f-110">Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} ^ {\lceil\ Log_2 N\rceıl} \ {0} Tus^ {k} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _j}.</span><span class="sxs-lookup"><span data-stu-id="01a0f-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="01a0f-111">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="01a0f-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="01a0f-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="01a0f-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="01a0f-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01a0f-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01a0f-114">Hedef hata $ \ Epsilon $.</span><span class="sxs-lookup"><span data-stu-id="01a0f-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="01a0f-115">katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="01a0f-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="01a0f-116">Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.</span><span class="sxs-lookup"><span data-stu-id="01a0f-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="01a0f-117">Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="01a0f-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="01a0f-118">Çıkış: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL)</span><span class="sxs-lookup"><span data-stu-id="01a0f-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="01a0f-119">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="01a0f-119">First parameter</span></span>

<span data-ttu-id="01a0f-120">`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.</span><span class="sxs-lookup"><span data-stu-id="01a0f-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="01a0f-121">İkinci parametre</span><span class="sxs-lookup"><span data-stu-id="01a0f-121">Second parameter</span></span>

<span data-ttu-id="01a0f-122">Katsayı dizisinin tek norm $ \ sum_j | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="01a0f-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="01a0f-123">Üçüncü parametre</span><span class="sxs-lookup"><span data-stu-id="01a0f-123">Third parameter</span></span>

<span data-ttu-id="01a0f-124">Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="01a0f-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="01a0f-125">Başvurular</span><span class="sxs-lookup"><span data-stu-id="01a0f-125">References</span></span>

- <span data-ttu-id="01a0f-126">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="01a0f-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>