---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728226"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="aa9a6-102">EstimateFrequencyA işlemi</span><span class="sxs-lookup"><span data-stu-id="aa9a6-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="aa9a6-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="aa9a6-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="aa9a6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa9a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa9a6-105">Adjointable ve ölçüm olan bir hazırlık verildiğinde, `Zero` belirli bir deneme sayısı gerçekleştirerek, ölçümün başarılı olduğu sıklığı (döndürür) tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="aa9a6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="aa9a6-106">Input</span></span>

### <a name="preparation--qubit--unit-adj"></a><span data-ttu-id="aa9a6-107">Hazırlık: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="aa9a6-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aa9a6-108">Giriş kaydına verilen bir durum $ \rho $ hazırlayan bir adjointable işlemi $P $.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="aa9a6-109">ölçüm: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="aa9a6-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="aa9a6-110">Bir işlem, ilgilendiğiniz ölçümü temsil eden $M.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="aa9a6-111">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa9a6-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa9a6-112">Her birinin hazırlanması ve ölçüsünün işlem yapması gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="aa9a6-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="aa9a6-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="aa9a6-114">İlgilendiğiniz sıklığı tahmin etmek için ölçümün kaç kez gerçekleştirilmesi gerektiği.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="aa9a6-115">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aa9a6-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aa9a6-116">$M sıklığı (p (\ket{00 \ cnoktalar 0} \bra{00 \ cnoktalar 0})) $ işlevinin tahmini bir $ \hat{p} $ `Zero` \_ \_ $n \_ {\upoklu} $, gözlenen sonuçların sayısıdır ve bu, {\upoklu} $, gözlenmemiş binom tahmin aracı $ \hat{p} = n {\upoklu}/n {\Text{measurements}} $ kullanılarak elde edilir `Zero` .</span><span class="sxs-lookup"><span data-stu-id="aa9a6-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa9a6-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aa9a6-117">Remarks</span></span>

<span data-ttu-id="aa9a6-118">Adjointable işlemleri için, işlemi çağırma gibi bazı varsayımlar, hedef makinelerin bazı performans iyileştirmeleri yapmasına izin veren qubits 'i tam olarak aynı duruma hazırlar.</span><span class="sxs-lookup"><span data-stu-id="aa9a6-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>