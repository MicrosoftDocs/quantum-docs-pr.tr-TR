---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Oracletoayrık işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733359"
---
# <a name="oracletodiscrete-function"></a>Oracletoayrık işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


"Siyah kutu" Oracle 'ı temsil eden bir işlem verildiğinde, "siyah kutu" Oracle 'ın birden çok kez tekrarlandığı bir bağımsız Oracle döndürür.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Giriş

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>BlackICE. BlackICE: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

Üs olacak işlem.



## <a name="output--discreteoracle"></a>Çıkış: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Bir işlem, "siyah kutu" Oracle üzerinde kısmen uygulanmış ve ayrı zaman Oracle 'ı temsil eder