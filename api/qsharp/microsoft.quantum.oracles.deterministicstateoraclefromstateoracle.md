---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226766"
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