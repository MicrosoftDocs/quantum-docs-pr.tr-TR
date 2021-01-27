---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842498"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Oracle türünü öğesine dönüştürür `DeterministicStateOracle` `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Giriş

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Bir durum hazırlama Oracle $A $ türü `DeterministicStateOracle` .



## <a name="output--stateoracle"></a>Çıkış: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Aynı durum hazırlama Oracle $A $, ancak şimdi türü `StateOracle` . Bu, içindeki bayrak dizininin `StateOracle` bir kukla değişken olduğunu ve hiçbir etkiye sahip olmadığını unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. hisse. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)