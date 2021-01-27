---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: Yaklaşık Teınputencoder işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856173"
---
# <a name="approximateinputencoder-function"></a>Yaklaşık Teınputencoder işlevi

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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