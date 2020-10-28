---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726629"
---
# <a name="labeledsample-user-defined-type"></a>LabeledSample Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Örnek ait olduğu sınıf ile etiketlenmiş bir örnek.

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="features--double"></a>Özellikler: [Double](xref:microsoft.quantum.lang-ref.double)[]

Verilen örnek için bir özellik vektörü.
### <a name="label--int"></a>Etiket: [Int](xref:microsoft.quantum.lang-ref.int)

Bu örneğin ait olduğu sınıf için bir tamsayı etiketi.