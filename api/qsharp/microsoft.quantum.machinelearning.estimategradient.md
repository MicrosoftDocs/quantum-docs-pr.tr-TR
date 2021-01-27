---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844393"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="c6692-102">EstimateGradient işlemi</span><span class="sxs-lookup"><span data-stu-id="c6692-102">EstimateGradient operation</span></span>

<span data-ttu-id="c6692-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c6692-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c6692-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c6692-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c6692-105">Belirli bir modelde ve belirli bir kodlanmış giriş için sıralı bir sınıflandırıcı için eğitim degradesini tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="c6692-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="c6692-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c6692-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="c6692-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c6692-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c6692-108">Gradyanı tahmini olan sıralı model.</span><span class="sxs-lookup"><span data-stu-id="c6692-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="c6692-109">Encodedınput: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="c6692-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="c6692-110">Bir durum hazırlama işleminde kodlanan sıralı sınıflandırıcının girişi.</span><span class="sxs-lookup"><span data-stu-id="c6692-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="c6692-111">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6692-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6692-112">Degradeyi tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6692-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="c6692-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="c6692-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="c6692-114">Verilen giriş ve model parametrelerinde eğitim gradyanının tahmini.</span><span class="sxs-lookup"><span data-stu-id="c6692-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6692-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c6692-115">Remarks</span></span>

<span data-ttu-id="c6692-116">Bu işlem, degradeyi tahmin etmek için bir Hadamard testi ve parametre kaydırma tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="c6692-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>