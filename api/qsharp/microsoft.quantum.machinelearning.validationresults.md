---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846086"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Bir sınıflandırıcının bir örnek kümesiyle doğrulanması için sonuçlar.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="nmisclassifications--int"></a>NHatalı sınıflandırmalar: [Int](xref:microsoft.quantum.lang-ref.int)

Doğrulama sırasında gözlemlenen hatalı sınıflandırmaların sayısı.
### <a name="nvalidationsamples--int"></a>NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)

