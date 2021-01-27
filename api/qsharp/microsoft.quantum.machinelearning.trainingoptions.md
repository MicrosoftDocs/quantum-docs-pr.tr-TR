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
# <a name="trainingoptions-user-defined-type"></a>Traıningoptions Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Başvurular

- [Arxıv: 1804.00633](https://arxiv.org/abs/1804.00633)