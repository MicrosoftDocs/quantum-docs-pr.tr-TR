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
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="d57ea-102">ContinuousOracle Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="d57ea-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="d57ea-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="d57ea-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="d57ea-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d57ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d57ea-105">Sürekli bir Oracle 'ı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="d57ea-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="d57ea-106">Bu, $U $ ' in sabit bir işlem olduğu ve $ \delta t $ ' un negatif olmayan bir gerçek sayı olduğu her zaman için $U (\delta t): \ket{\psı (t)} \mapsto \ket{\psı (t + \delta t)} $ $t uygulayan bir Oracle ' dır.</span><span class="sxs-lookup"><span data-stu-id="d57ea-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

