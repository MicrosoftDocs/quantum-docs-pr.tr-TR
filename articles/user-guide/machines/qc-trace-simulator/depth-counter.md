---
title: Derinlik sayacı
description: Hisse bir programda çağrılan her işlemin derinlik sayısını toplayan Microsoft QDK derinlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415288"
---
# <a name="depth-counter"></a>Derinlik sayacı

, `Depth Counter` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır.
Bir hisse bir programda çağrılan her işlemin derinliğine yönelik alt sınırı temsil eden sayıları toplamak için kullanılır. ' Den tüm işlemler <xref:microsoft.quantum.intrinsic> tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

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
