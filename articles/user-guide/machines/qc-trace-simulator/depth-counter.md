---
title: Derinlik sayacı-hisse geliştirme seti
description: Bir programda çağrılan her işlemin derinlik sayısını toplamak için hisse izi simülatörü kullanan Microsoft QDK derinlik sayacı hakkında bilgi edinin Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692102"
---
# <a name="quantum-trace-simulator-depth-counter"></a>Hisse izleme simülatörü: derinlik sayacı

Derinlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.
Bu işlemi, bir hisse dosyasında çağrılan her işlemin derinliğine ait derinlik alt sınırını temsil eden sayıları toplamak için kullanabilirsiniz. 

## <a name="depth-values"></a>Derinlik değerleri

Varsayılan olarak, tüm işlemler, **0** `T` **1** derinliğine sahip olan işlem haricinde 0 derinliğine sahiptir. Bu, varsayılan olarak yalnızca `T` işlemlerin derinliğini (çoğunlukla tercih edilir) hesaplandığı anlamına gelir. Derinlik sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarındaki istatistikleri toplar ve toplar.

Tüm <xref:Microsoft.Quantum.Intrinsic> işlemler tek qubit döndürmeler, <xref:Microsoft.Quantum.Intrinsic.T> işlemler, tek qubit Clienfford işlemleri, <xref:Microsoft.Quantum.Intrinsic.CNOT> işlemler ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Kullanıcılar, alanı aracılığıyla temel işlemlerin her biri için derinlik ayarlayabilir `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> .

## <a name="invoking-the-depth-counter"></a>Derinlik sayacını çağırma

Hisse izi izleme simülatörünü derinlik sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliğini true olarak ayarlamanız `UseDepthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` . 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>C# ana programında derinlik sayacını kullanma

Bu bölümde takip edilen C# örneği `T` `CCNOT` , aşağıdaki örnek koda göre işlemin derinliğini hesaplar Q# :

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Bunun derinliğine sahip olup olmadığını denetlemek için `CCNOT` `T` **5** `ApplySampleWithCCNOT` `T` aşağıdaki **6** C# kodunu kullanın:

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

Programın ilk kısmı çalışır `ApplySampleWithCCNOT` . İkinci bölüm, [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ve derinliğini almak için yöntemini kullanır `T` `CCNOT` `ApplySampleWithCCNOT` . 

Son olarak, aşağıdaki kullanarak, derinlik sayacı tarafından toplanan tüm istatistiklerin CSV biçiminde çıktısını alabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>Ayrıca bkz.

- Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API başvurusu.
