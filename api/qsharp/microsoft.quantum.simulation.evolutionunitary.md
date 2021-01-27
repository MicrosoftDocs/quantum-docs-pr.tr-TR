---
uid: Microsoft.Quantum.Simulation.EvolutionUnitary
title: EvolutionUnitary Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EvolutionUnitary
qsharp.summary: >-
  Represents a unitary time-evolution operator.

  The first parameter is is duration of time-evolution, and the second parameter is the qubit register acted upon by the unitary.
ms.openlocfilehash: ea160bb9a0a8bb5106c3e37a6a16155bad71dd25
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856052"
---
# <a name="evolutionunitary-user-defined-type"></a>EvolutionUnitary Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Unitary zaman-gelişme işlecini temsil eder.

İlk parametre zaman evrimi olur ve ikinci parametre Unitary tarafından üzerinde işlem yapan qubit kayıt olur.

```qsharp

newtype EvolutionUnitary = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

