---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731055"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Bir sınıflandırıcının bir örnek kümesiyle doğrulanması için sonuçlar.

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="nmisclassifications--int"></a>NHatalı sınıflandırmalar: [Int](xref:microsoft.quantum.lang-ref.int)

Doğrulama sırasında gözlemlenen hatalı sınıflandırmaların sayısı.
### <a name="nvalidationsamples--int"></a>NValidationSamples: [Int](xref:microsoft.quantum.lang-ref.int)

