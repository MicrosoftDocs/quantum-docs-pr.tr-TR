---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Randomwalkphasetahmine işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846011"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="92ca3-102">Randomwalkphasetahmine işlemi</span><span class="sxs-lookup"><span data-stu-id="92ca3-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="92ca3-103">Ad alanı: [Microsoft. hisse. araştırma. karakterleştirme](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="92ca3-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="92ca3-104">Paket: [Microsoft. hisse. araştırma. karakterleştirme](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="92ca3-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="92ca3-105">Belirli bir Oracle ve eigenstate 'teki klasik ölçüm sonuçlarında Bayeduyma çıkarımı için rastgele bir adım kullanarak yinelemeli aşama tahmini gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="92ca3-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="92ca3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="92ca3-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="92ca3-107">ınitialortalama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92ca3-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92ca3-108">$ \Phi $ üzerinden ilk normal önceki dağıtım ortalaması.</span><span class="sxs-lookup"><span data-stu-id="92ca3-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="92ca3-109">ınitialstddev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92ca3-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92ca3-110">$ \Phi $ üzerinden ilk normal önceki dağıtımın standart sapması.</span><span class="sxs-lookup"><span data-stu-id="92ca3-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="92ca3-111">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92ca3-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92ca3-112">Son posterior tahmine kabul edilecek ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="92ca3-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="92ca3-113">Maxölçüler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92ca3-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92ca3-114">İşlemin başarısız olduğu kabul edilmeden önce alınabilecek toplam ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="92ca3-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="92ca3-115">geriye doğru izleme: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="92ca3-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="92ca3-116">Tutarlılık denetimi başarısız olduğunda unutmak için sonuç sayısı.</span><span class="sxs-lookup"><span data-stu-id="92ca3-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="92ca3-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="92ca3-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="92ca3-118">Bir Unitary $U $ öğesini temsil eden bir işlem, $U (t) \ket{\phi} = e ^ {ı t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ için bilinmeyen aşama $ \phi \ \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="92ca3-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="92ca3-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="92ca3-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="92ca3-120">$U $ üzerinde hareket eden bir kayıt.</span><span class="sxs-lookup"><span data-stu-id="92ca3-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="92ca3-121">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92ca3-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92ca3-122">Son tahmin $ \hat{\phi} \mathrel{: =} \beklediği [\phi] $, burada beklenmenin, kabul edilen tüm veriler verildiğinde posterior üzerinde olduğu.</span><span class="sxs-lookup"><span data-stu-id="92ca3-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="92ca3-123">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="92ca3-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="92ca3-124">Yinelemeli aşama tahmini ve Eigenstates</span><span class="sxs-lookup"><span data-stu-id="92ca3-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="92ca3-125">Genel olarak, giriş kaydının `eigenstate` bir eigenstate $ \ket{\phi} $ $U $ olması gerekmez, ancak eigenstates üzerinde bir üst konum olabilir.</span><span class="sxs-lookup"><span data-stu-id="92ca3-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="92ca3-126">Giriş durumunun \begin{hizalaması} \ket{\psı} & = \sum \_ {j} \Alpha \_ j \ket{\phi j} tarafından verildiğini varsayalım. \_ \end{hizalaması}; $ \{ \Alpha j \_ \} $, $ \sum \_ j | \alpha \_ j | ^ 2 = $1 ve $U \ket{\phi \_ j} = \phi \_ j\tus{\ Phi \_ j} $ gibi karmaşık katlardır.</span><span class="sxs-lookup"><span data-stu-id="92ca3-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="92ca3-127">Daha sonra, yinelemeli aşama tahmini gerçekleştirmek [geliştirme kılavuzunda](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)açıklandığı gibi, sonunda tek bir eigenstate 'e yakınsayacaktır.</span><span class="sxs-lookup"><span data-stu-id="92ca3-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="92ca3-128">Deneme tasarımı</span><span class="sxs-lookup"><span data-stu-id="92ca3-128">Experiment Design</span></span>

<span data-ttu-id="92ca3-129">$T $ ve Inversion açıları $ \teta $ öğesine geçirilen ölçüm süreleri `oracle` , *parçacık tahmin buluşsal* yöntemi, \begin{hizalaması} \teta \ sim \pr (\fi), \dörtlü t \yaklaşık \frac {1} {\variance{\phi}} öğesine göre seçilir.</span><span class="sxs-lookup"><span data-stu-id="92ca3-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="92ca3-130">\end{hizalaması} bu buluşsal yöntemi, daha önce normal varsayımıyla, yinelemeli aşama tahminlerinde beklenen posterior varyansı azaltmak için idealdir.</span><span class="sxs-lookup"><span data-stu-id="92ca3-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="92ca3-131">Optimizasyonu</span><span class="sxs-lookup"><span data-stu-id="92ca3-131">Optimality</span></span>

<span data-ttu-id="92ca3-132">Bu işlem, ikinci dereceden kayıp $L (\fi, \hat{\phi}) \mathrel{: =} (\fi-\hat{\phi}) ^ 2 $ olarak değerlendirilen $ \phi $ aşaması için en uygun tahmin aracı 'a yaklaştırır.</span><span class="sxs-lookup"><span data-stu-id="92ca3-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="92ca3-133">Yinelemeli aşama tahmini istatistikleri hakkında daha fazla bilgi için bkz. [Bayeme aşaması tahmini](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .</span><span class="sxs-lookup"><span data-stu-id="92ca3-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="92ca3-134">Başvurular</span><span class="sxs-lookup"><span data-stu-id="92ca3-134">References</span></span>

- <span data-ttu-id="92ca3-135">Ferrie *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arxıv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="92ca3-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="92ca3-136">Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arxıv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="92ca3-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="92ca3-137">Wiebe ve granade 2018 *(hazırlık aşamasında)*.</span><span class="sxs-lookup"><span data-stu-id="92ca3-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>