---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196421"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Belirli bir özellik vektörünün kodlanması için gereken qubits sayısını döndürür.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Giriş

### <a name="sample--double"></a>Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]

Bir qubit kaydına kodlanacak örnek bir özellik vektörü.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Bir qubit kaydına kodlamak için gereken boyut `sample` , qubit sayısı olarak ifade edilir.