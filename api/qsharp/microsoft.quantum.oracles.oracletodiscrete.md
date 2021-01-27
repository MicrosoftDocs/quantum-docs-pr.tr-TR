---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Oracletoayrık işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842530"
---
# <a name="oracletodiscrete-function"></a>Oracletoayrık işlevi

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


"Siyah kutu" Oracle 'ı temsil eden bir işlem verildiğinde, "siyah kutu" Oracle 'ın birden çok kez tekrarlandığı bir bağımsız Oracle döndürür.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Giriş

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>BlackICE + CTL 'de kara Boxoracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)

Üs olacak işlem.



## <a name="output--discreteoracle"></a>Çıkış: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Bir işlem, "siyah kutu" Oracle üzerinde kısmen uygulanmış ve ayrı zaman Oracle 'ı temsil eder

## <a name="example"></a>Örnek

`OracleToDiscrete(U)(3, target)``U(target)`tekrararda üç kez eşdeğerdir.