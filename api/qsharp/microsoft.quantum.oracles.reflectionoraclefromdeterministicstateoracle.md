---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842522"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Oracle 'dan belirli bir durum hakkında yansıma oluşturur.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Description

Bir Unitary matrisi tarafından temsil edilen bir belirleyici durum hazırlama $O $, bu işlevin sonucu, Oracle $O $; tarafından hazırlanan $ \ket{\psı} $ durumunun etrafında bir yansıma uygulayan bir Oracle olur. diğer bir deyişle, $ \ket{\psı} $, $O {0} \tus= \ket{\psı} $ şeklindedir.

## <a name="input"></a>Giriş

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

$ \Ket{\psı} $ durumunun kopyalarını hazırlayan bir Oracle.



## <a name="output--reflectionoracle"></a>Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

$ \Ket{\psı} $ durumunu yansıtan bir Oracle.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. hisse. Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)