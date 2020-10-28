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
# <a name="trainingoptions-user-defined-type"></a>Traıningoptions Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Eğitim hisse sınıflandırıcıları içinde kullanılacak seçenekler koleksiyonu.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="learningrate--double"></a>Leardokgrate: [Double](xref:microsoft.quantum.lang-ref.double)

Eğitim adımları sırasında model parametreleri güncelleştirilirken degradelerin ölçeklendirildi olması gereken öğrenme oranı.
### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Örnekleri hisse eyalet olarak hazırlarken kullanılacak yaklaşık tolerans.
### <a name="minibatchsize--int"></a>Mini BatchSize: [Int](xref:microsoft.quantum.lang-ref.int)

Her eğitim mini toplu işleminde kullanılacak örnek sayısı.
### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Sınıflandırma olasılığının tahmin edilmesi için her sınıflandırma sonucunun ölçülme sayısı.
### <a name="maxepochs--int"></a>Maxdönemler CHS: [Int](xref:microsoft.quantum.lang-ref.int)

Her model için eğen maksimum dönemler sayısı.
### <a name="maxstalls--int"></a>Maxtakılması: [Int](xref:microsoft.quantum.lang-ref.int)

Bir eğitim dönemi başarısız olmadan önce (yaklaşık sıfır gradyan) izin verilen en fazla deneme sayısı.
### <a name="stochasticrescalefactor--double"></a>Stochasticrescalefaktör: [Double](xref:microsoft.quantum.lang-ref.double)

Bir güncelleştirmeyi yeniden denemeden önce tarafından durdurulmuş modelleri yeniden ölçeklendirme miktarı.
### <a name="scoringperiod--int"></a>ScoringPeriod: [Int](xref:microsoft.quantum.lang-ref.int)

Puanlama noktaları arasında gerçekleştirilecek gradyan adımları sayısı.
En iyi doğruluk için 1 olarak ayarlayın.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [dize](xref:microsoft.quantum.lang-ref.string) -> [birimi](xref:microsoft.quantum.lang-ref.unit)

Ayrıntılı geri bildirim sağlamak için kullanılabilen bir işlev.

## <a name="remarks"></a>Açıklamalar

Bu UDT doğrudan oluşturulmamalıdır, ancak bunun yerine @"microsoft.quantum.machinelearning.defaulttrainingoptions" `w/` farklı Varsayılanları geçersiz kılmak için işleci kullanılarak belirtilmelidir.

Örneğin, 100.000 ölçümleri ve en fazla 8 eğitim dönemlerinde kullanmak için:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Referanslar

- [Arxıv: 1804.00633](https://arxiv.org/abs/1804.00633)