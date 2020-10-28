---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733399"
---
# <a name="continuousoracle-user-defined-type"></a>ContinuousOracle Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


Sürekli bir Oracle 'ı temsil eder.

Bu, $U $ ' in sabit bir işlem olduğu ve $ \delta t $ ' un negatif olmayan bir gerçek sayı olduğu her zaman için $U (\delta t): \ket{\psı (t)} \mapsto \ket{\psı (t + \delta t)} $ $t uygulayan bir Oracle ' dır.

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

