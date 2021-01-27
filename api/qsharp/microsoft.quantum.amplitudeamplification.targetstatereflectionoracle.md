---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Targetstatereflictionoracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 4169ccf3e210e27f779311553b845ea04f2c7dc6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843900"
---
# <a name="targetstatereflectionoracle-function"></a>Targetstatereflictionoracle işlevi

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`ReflectionOracle`Benzersiz olarak bayrak qubit tarafından işaretlenen hedef durumu hakkında bir oluşturur.

Hedef durumu 1 olarak ayarlanmış tek bir qubit ve diğerleri 0: $ \ demet {1} _F $ şeklindedir.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Giriş

### <a name="idxflagqubit--int"></a>ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)

Oracle 'ın $f $ ' nin işaret edeceği dizin.



## <a name="output--reflectionoracle"></a>Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

`ReflectionOracle`$ \Ket _F $ tarafından işaretlenen durumu yansıtan bir {1} .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)