---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855927"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sürekli bir Oracle 'ı temsil eder.

Bu, $U $ ' in sabit bir işlem olduğu ve $ \delta t $ ' un negatif olmayan bir gerçek sayı olduğu her zaman için $U (\delta t): \ket{\psı (t)} \mapsto \ket{\psı (t + \delta t)} $ $t uygulayan bir Oracle ' dır.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

