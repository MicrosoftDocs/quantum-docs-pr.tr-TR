---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216260"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="b0d22-102">EstimateFrequency işlemi</span><span class="sxs-lookup"><span data-stu-id="b0d22-102">EstimateFrequency operation</span></span>

<span data-ttu-id="b0d22-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="b0d22-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="b0d22-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0d22-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0d22-105">Hazırlık ve ölçüm verildiğinde, `Zero` belirli bir deneme sayısı gerçekleştirerek, ölçümün başarılı olduğu sıklığı (döndürür) tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="b0d22-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="b0d22-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b0d22-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="b0d22-107">Hazırlık: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0d22-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b0d22-108">Giriş kaydı üzerinde verilen bir durum $ \rho $ hazırlayan bir işlem $P $.</span><span class="sxs-lookup"><span data-stu-id="b0d22-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="b0d22-109">ölçüm: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="b0d22-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="b0d22-110">Bir işlem, ilgilendiğiniz ölçümü temsil eden $M.</span><span class="sxs-lookup"><span data-stu-id="b0d22-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="b0d22-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0d22-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0d22-112">Her birinin hazırlanması ve ölçüsünün işlem yapması gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="b0d22-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="b0d22-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0d22-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0d22-114">İlgilendiğiniz sıklığı tahmin etmek için ölçümün kaç kez gerçekleştirilmesi gerektiği.</span><span class="sxs-lookup"><span data-stu-id="b0d22-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="b0d22-115">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b0d22-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b0d22-116">$M sıklığı (p (\ket{00 \ cnoktalar 0} \bra{00 \ cnoktalar 0})) $ işlevinin tahmini bir $ \hat{p} $ `Zero` \_ \_ $n \_ {\upoklu} $, gözlenen sonuçların sayısıdır ve bu, {\upoklu} $, gözlenmemiş binom tahmin aracı $ \hat{p} = n {\upoklu}/n {\Text{measurements}} $ kullanılarak elde edilir `Zero` .</span><span class="sxs-lookup"><span data-stu-id="b0d22-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="b0d22-117">Bu, olasılıkların ölçülemez olması gibi fiziksel sınırlamalara yönelik hedef makinelerde özellikle önemlidir.</span><span class="sxs-lookup"><span data-stu-id="b0d22-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>