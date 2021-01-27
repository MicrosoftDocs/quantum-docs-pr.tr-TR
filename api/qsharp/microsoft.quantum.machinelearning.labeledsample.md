---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846972"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Örnek ait olduğu sınıf ile etiketlenmiş bir örnek.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="features--double"></a>Özellikler: [Double](xref:microsoft.quantum.lang-ref.double)[]

Verilen örnek için bir özellik vektörü.
### <a name="label--int"></a>Etiket: [Int](xref:microsoft.quantum.lang-ref.int)

Bu örneğin ait olduğu sınıf için bir tamsayı etiketi.