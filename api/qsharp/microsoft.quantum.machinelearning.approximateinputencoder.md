---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Yaklaşık Teınputencoder işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731127"
---
# <a name="approximateinputencoder-function"></a>Yaklaşık Teınputencoder işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Bir katsayı ve tolerans kümesi verildiğinde, her katsayısını, belirtilen toleranstan kadar bir hesaplama tabanlı durumu olarak hazırlayan bir durum hazırlama işlemi döndürür.

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Verilen katsayılarını bir giriş durumuna kodlarken kullanılacak yaklaşık tolerans.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Bir giriş durumuna kodlanacak katsayılar.



## <a name="output--stategenerator"></a>Çıkış: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Verilen katsayılarını belirli bir kayıttaki giriş durumu olarak hazırlayan bir durum hazırlama işlemi.