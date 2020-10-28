---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732178"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


Bir Oracle 'dan belirli bir durum hakkında yansıma oluşturur.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Açıklama

Bir Unitary matrisi tarafından temsil edilen bir belirleyici durum hazırlama $O $, bu işlevin sonucu, Oracle $O $; tarafından hazırlanan $ \ket{\psı} $ durumunun etrafında bir yansıma uygulayan bir Oracle olur. diğer bir deyişle, $ \ket{\psı} $, $O {0} \tus= \ket{\psı} $ şeklindedir.

## <a name="input"></a>Giriş

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

$ \Ket{\psı} $ durumunun kopyalarını hazırlayan bir Oracle.



## <a name="output--reflectionoracle"></a>Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

$ \Ket{\psı} $ durumunu yansıtan bir Oracle.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. hisse. Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)