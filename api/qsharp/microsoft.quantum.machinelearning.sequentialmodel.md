---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854888"
---
# <a name="sequentialmodel-user-defined-type"></a>SequentialModel Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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

## <a name="references"></a>Başvurular

- [Arxıv: 1804.00633](https://arxiv.org/abs/1804.00633)