---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854958"
---
# <a name="nqubitsrequired-function"></a>NQubitsRequired işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Belirli bir sıralı sınıflandırıcının uygulanması için gereken qubits sayısını döndürür.

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a>Giriş

### <a name="model--sequentialmodel"></a>Model: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Sıralı sınıflandırıcının uygulanabileceğini en küçük bir kayıt boyutu.