---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: c7aa80feda67d68216f318073ee8c6a5eb0653c0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854521"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>ObliviousOracleFromDeterministicStateOracle işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oracles ve birleştirir `DeterministicStateOracle` `ObliviousOracle` .

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>Giriş

### <a name="ancillaoracle--deterministicstateoracle"></a>Anlanlaoracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Bir durum hazırlama Oracle $A $, `DeterministicStateOracle` kayıt $a $ üzerinde işlem gören tür $.


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

`ObliviousOracle`Kayıt $a, s $ üzerinde ortaklaşa çalışan bir oracle $U $ türü.



## <a name="output--obliviousoracle"></a>Çıkış: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Bir Oracle $O = UA $ türü `ObliviousOracle` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. hisse. Oracles. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)