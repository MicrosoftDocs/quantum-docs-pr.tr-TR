---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731114"
---
# <a name="combinedstructure-function"></a>CombinedStructure işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Denetlenen bir veya daha fazla yönetim katmanı, farklı katmanlar ayrı model parametrelerine göre parametreleştirileyecek şekilde, model parametre dizini kaydırılan tek bir katman döndürür.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Giriş

### <a name="layers--controlledrotation"></a>katmanlar: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

Birleştirilecek katmanlar.



## <a name="output--controlledrotation"></a>Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Diğer tüm katmanların birleştirilmesiyle temsil eden, tek bir kontrollü tek katman.