---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211976"
---
# <a name="combinedstructure-function"></a>CombinedStructure işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Denetlenen bir veya daha fazla yönetim katmanı, farklı katmanlar ayrı model parametrelerine göre parametreleştirileyecek şekilde, model parametre dizini kaydırılan tek bir katman döndürür.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Giriş

### <a name="layers--controlledrotation"></a>katmanlar: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Birleştirilecek katmanlar.



## <a name="output--controlledrotation"></a>Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Diğer tüm katmanların birleştirilmesiyle temsil eden, tek bir kontrollü tek katman.