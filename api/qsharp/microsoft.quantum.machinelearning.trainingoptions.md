---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: Traıningoptions Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842776"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="d8878-102">Traıningoptions Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="d8878-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="d8878-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d8878-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d8878-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d8878-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d8878-105">Eğitim hisse sınıflandırıcıları içinde kullanılacak seçenekler koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="d8878-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="d8878-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="d8878-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="d8878-107">Leardokgrate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8878-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8878-108">Eğitim adımları sırasında model parametreleri güncelleştirilirken degradelerin ölçeklendirildi olması gereken öğrenme oranı.</span><span class="sxs-lookup"><span data-stu-id="d8878-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="d8878-109">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8878-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8878-110">Örnekleri hisse eyalet olarak hazırlarken kullanılacak yaklaşık tolerans.</span><span class="sxs-lookup"><span data-stu-id="d8878-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="d8878-111">Mini BatchSize: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8878-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8878-112">Her eğitim mini toplu işleminde kullanılacak örnek sayısı.</span><span class="sxs-lookup"><span data-stu-id="d8878-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="d8878-113">Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8878-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8878-114">Sınıflandırma olasılığının tahmin edilmesi için her sınıflandırma sonucunun ölçülme sayısı.</span><span class="sxs-lookup"><span data-stu-id="d8878-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="d8878-115">Maxdönemler CHS: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8878-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8878-116">Her model için eğen maksimum dönemler sayısı.</span><span class="sxs-lookup"><span data-stu-id="d8878-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="d8878-117">Maxtakılması: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8878-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8878-118">Bir eğitim dönemi başarısız olmadan önce (yaklaşık sıfır gradyan) izin verilen en fazla deneme sayısı.</span><span class="sxs-lookup"><span data-stu-id="d8878-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="d8878-119">Stochasticrescalefaktör: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d8878-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d8878-120">Bir güncelleştirmeyi yeniden denemeden önce tarafından durdurulmuş modelleri yeniden ölçeklendirme miktarı.</span><span class="sxs-lookup"><span data-stu-id="d8878-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="d8878-121">ScoringPeriod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8878-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8878-122">Puanlama noktaları arasında gerçekleştirilecek gradyan adımları sayısı.</span><span class="sxs-lookup"><span data-stu-id="d8878-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="d8878-123">En iyi doğruluk için 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="d8878-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="d8878-124">VerboseMessage: [dize](xref:microsoft.quantum.lang-ref.string) -> [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8878-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="d8878-125">Ayrıntılı geri bildirim sağlamak için kullanılabilen bir işlev.</span><span class="sxs-lookup"><span data-stu-id="d8878-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="d8878-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d8878-126">Remarks</span></span>

<span data-ttu-id="d8878-127">Bu UDT doğrudan oluşturulmamalıdır, ancak bunun yerine @"microsoft.quantum.machinelearning.defaulttrainingoptions" `w/` farklı Varsayılanları geçersiz kılmak için işleci kullanılarak belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="d8878-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="d8878-128">Örneğin, 100.000 ölçümleri ve en fazla 8 eğitim dönemlerinde kullanmak için:</span><span class="sxs-lookup"><span data-stu-id="d8878-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="d8878-129">Başvurular</span><span class="sxs-lookup"><span data-stu-id="d8878-129">References</span></span>

- [<span data-ttu-id="d8878-130">Arxıv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="d8878-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)