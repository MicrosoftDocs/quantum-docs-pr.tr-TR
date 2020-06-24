---
title: Derinlik sayacı
description: Hisse bir programda çağrılan her işlemin derinlik sayısını toplayan Microsoft QDK derinlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275631"
---
# <a name="depth-counter"></a>Derinlik sayacı

, `Depth Counter` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır.
Hisse bir programda çağrılan her işlemin derinlik sayısını toplamak için kullanılır. ' Den tüm işlemler <xref:microsoft.quantum.intrinsic> tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

Varsayılan olarak, tüm işlemler, 1 derinliğine sahip T kapısı dışında derinlik 0 ' dır. Bu, varsayılan olarak yalnızca T ve Operations 'in yalnızca T derinliğini hesaplandığı anlamına gelir (Bu genellikle tercih edilir). Toplanan istatistikler, işlemler çağrı grafiğinin tüm kenarlarına toplanır. 

Şimdi işlemin derinliğini hesaplamıza izin verin <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> . Aşağıdaki Q # örnek kodunu kullanacağız:

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>C# programı içinde derinlik sayacı kullanma

Bunun derinliğine sahip olup olmadığını denetlemek için `CCNOT` `T` `ApplySampleWithCCNOT` `T` Aşağıdaki C# kodunu kullanabiliriz:

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

Programın ilk kısmı yürütülür `ApplySampleWithCCNOT` . İkinci bölümde, `QCTraceSimulator.GetMetric` ve derinliğini almak için yöntemini kullanıyoruz `T` `CCNOT` `ApplySampleWithCCNOT` : 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Son olarak, CSV biçiminde toplanan tüm istatistiklerin çıktısını almak için `Depth Counter` aşağıdakileri kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
