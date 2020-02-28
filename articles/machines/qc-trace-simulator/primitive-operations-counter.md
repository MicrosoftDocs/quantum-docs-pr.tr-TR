---
title: Temel Işlem sayacı
description: Bir hisse bir programdaki işlemler tarafından kullanılan temel yürütmelerin sayısını izleyen Microsoft QDK temel Işlem sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905956"
---
# <a name="primitive-operations-counter"></a>Temel Işlem sayacı  

`Primitive Operations Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar. `Microsoft.Quantum.Intrinsic` tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır. Şimdi `CCNOT` işleminin uygulanması için kaç `T` kapısı gerektiğini sayalım. 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Bir C# program Içinde temel işlem sayacını kullanma

`CCNOT`, gerçekten 7 `T` kapısı gerektirdiğini ve `ApplySampleWithCCNOT` 8 `T` kapıları yürüttüğünü denetlemek için aşağıdaki C# kodu kullanabiliriz:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Programın ilk kısmı `ApplySampleWithCCNOT`yürütür. İkinci bölümde, `ApplySampleWithCCNOT`tarafından yürütülen T kapıları sayısını almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

`GetMetric` iki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür. Örnek işlem `Primitive.CCNOT` `ApplySampleWithCCNOT` içinde çağrılır ve bu nedenle çağrı grafı Edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`içerir. 

Kullanılan `CNOT` kapıları sayısını almak için aşağıdaki satırı ekleyebiliriz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
