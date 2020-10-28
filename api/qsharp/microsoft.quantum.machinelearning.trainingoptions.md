---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Traıningoptions Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732290"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="b5ad2-102">Traıningoptions Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="b5ad2-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="b5ad2-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b5ad2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b5ad2-105">Eğitim hisse sınıflandırıcıları içinde kullanılacak seçenekler koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="b5ad2-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="b5ad2-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="b5ad2-107">Leardokgrate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5ad2-108">Eğitim adımları sırasında model parametreleri güncelleştirilirken degradelerin ölçeklendirildi olması gereken öğrenme oranı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="b5ad2-109">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5ad2-110">Örnekleri hisse eyalet olarak hazırlarken kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="b5ad2-111">Mini BatchSize: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ad2-112">Her eğitim mini toplu işleminde kullanılacak örnek sayısı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="b5ad2-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ad2-114">Sınıflandırma olasılığının tahmin edilmesi için her sınıflandırma sonucunun ölçülme sayısı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="b5ad2-115">Maxdönemler CHS: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ad2-116">Her model için eğen maksimum dönemler sayısı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="b5ad2-117">Maxtakılması: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ad2-118">Bir eğitim dönemi başarısız olmadan önce (yaklaşık sıfır gradyan) izin verilen en fazla deneme sayısı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="b5ad2-119">Stochasticrescalefaktör: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b5ad2-120">Bir güncelleştirmeyi yeniden denemeden önce tarafından durdurulmuş modelleri yeniden ölçeklendirme miktarı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="b5ad2-121">ScoringPeriod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b5ad2-122">Puanlama noktaları arasında gerçekleştirilecek gradyan adımları sayısı.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="b5ad2-123">En iyi doğruluk için 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="b5ad2-124">VerboseMessage: [dize](xref:microsoft.quantum.lang-ref.string) -> [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5ad2-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="b5ad2-125">Ayrıntılı geri bildirim sağlamak için kullanılabilen bir işlev.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5ad2-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b5ad2-126">Remarks</span></span>

<span data-ttu-id="b5ad2-127">Bu UDT doğrudan oluşturulmamalıdır, ancak bunun yerine @"microsoft.quantum.machinelearning.defaulttrainingoptions" `w/` farklı Varsayılanları geçersiz kılmak için işleci kullanılarak belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="b5ad2-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="b5ad2-128">Örneğin, 100.000 ölçümleri ve en fazla 8 eğitim dönemlerinde kullanmak için:</span><span class="sxs-lookup"><span data-stu-id="b5ad2-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="b5ad2-129">Referanslar</span><span class="sxs-lookup"><span data-stu-id="b5ad2-129">References</span></span>

- [<span data-ttu-id="b5ad2-130">Arxıv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="b5ad2-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)