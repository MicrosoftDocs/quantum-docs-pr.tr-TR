---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732298"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Parametreli ve denetimli bir döndürmeler dizisinin, döndürme açılarından oluşan bir atamanın ve model tarafından tanınan iki sınıf arasındaki bir sapıcının oluşan bir hisse

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="structure--controlledrotation"></a>Yapı: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Girişleri sınıflandırmak için kullanılan denetlenen döndürmeler dizisi.
### <a name="parameters--double"></a>Parametreler: [Double](xref:microsoft.quantum.lang-ref.double)[]

Verilen sınıflandırma yapısına döndürme açıların atanması.
### <a name="bias--double"></a>Sapma: [Double](xref:microsoft.quantum.lang-ref.double)

Bu sınıflandırıcı tarafından tanınan iki sınıf arasındaki sapma.

## <a name="references"></a>Referanslar

- [Arxıv: 1804.00633](https://arxiv.org/abs/1804.00633)