---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854551"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Oracle türünü öğesine dönüştürür `StateOracle` `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Giriş

### <a name="idxflagqubit--int"></a>ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)

`stateOracle`İki kayıt üzerinde açıkça işlem gören $A $ bayrağının işaret eden dizin: $f $ bayrağı ve system $s $, örneğin $A {0} \_ \tusf\tus{\ PSI} \_ s $.


### <a name="stateoracle--stateoracle"></a>stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Bir durum hazırlama Oracle $A $ türü `StateOracle` .



## <a name="output--deterministicstateoracle"></a>Çıkış: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Aynı durum hazırlama Oracle $A $, ancak artık `DeterministicStateOracle` Bu nedenle, $a, s $ artık açıkça ayrısız bir kayıt üzerinde davranır, ör.  $A \ket{0\psı} \_ {as} $.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft. hisse. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)