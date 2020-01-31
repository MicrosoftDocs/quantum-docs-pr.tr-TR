---
title: Derinlik sayacı | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Kuantum bilgisayar izleme simülatörüne genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820479"
---
# <a name="depth-counter"></a>Derinlik sayacı

`Depth Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.
Hisse bir programda çağrılan her işlemin derinlik sayısını toplamak için kullanılır. <xref:microsoft.quantum.intrinsic> tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Kullanıcılar, <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>`gateTimes` alanı aracılığıyla temel işlemlerin her biri için derinlik belirleyebilir.

Varsayılan olarak, tüm işlemler, 1 derinliğine sahip T kapısı dışında derinlik 0 ' dır. Bu, varsayılan olarak yalnızca T ve Operations 'in yalnızca T derinliğini hesaplandığı anlamına gelir (Bu genellikle tercih edilir). Toplanan istatistikler, işlemler çağrı grafiğinin tüm kenarlarına toplanır. 

Şimdi <xref:microsoft.quantum.intrinsic.ccnot> işleminin <xref:microsoft.quantum.intrinsic.t> derinliğini hesaplamıza izin verin. Aşağıdaki Q # örnek kodunu kullanacağız:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>Bir C# program Içinde derinlik sayacı kullanma

`CCNOT` `T` Derinlik 5 ' i ve `ApplySampleWithCCNOT` `T` derinliğine sahip olduğunu denetlemek için aşağıdaki C# kodu kullanabilirsiniz:

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Programın ilk kısmı `ApplySampleWithCCNOT`yürütür. İkinci bölümde, `CCNOT` ve `ApplySampleWithCCNOT``T` derinliğini almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız: 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Son olarak, `Depth Counter` tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabiliriz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
