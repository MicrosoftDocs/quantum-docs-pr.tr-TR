---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730751"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="1ad4a-102">EstimateGradient işlemi</span><span class="sxs-lookup"><span data-stu-id="1ad4a-102">EstimateGradient operation</span></span>

<span data-ttu-id="1ad4a-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1ad4a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ad4a-105">Belirli bir modelde ve belirli bir kodlanmış giriş için sıralı bir sınıflandırıcı için eğitim degradesini tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="1ad4a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1ad4a-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="1ad4a-107">Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="1ad4a-108">Gradyanı tahmini olan sıralı model.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="1ad4a-109">Encodedınput: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="1ad4a-110">Bir durum hazırlama işleminde kodlanan sıralı sınıflandırıcının girişi.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1ad4a-111">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1ad4a-112">Degradeyi tahmin etmek için kullanılacak ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="1ad4a-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1ad4a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1ad4a-114">Verilen giriş ve model parametrelerinde eğitim gradyanının tahmini.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ad4a-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1ad4a-115">Remarks</span></span>

<span data-ttu-id="1ad4a-116">Bu işlem, degradeyi tahmin etmek için bir Hadamard testi ve parametre kaydırma tekniğini kullanır.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>