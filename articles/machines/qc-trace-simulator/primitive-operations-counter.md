---
title: Temel Işlem sayacı | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Hisse bilgisayar izleme simülatörünü genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184891"
---
# <a name="primitive-operations-counter"></a>Temel Işlem sayacı  

`Primitive Operations Counter`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar. `Microsoft.Quantum.Primitive` tüm işlemler tek qubit döndürmeler, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır. Şimdi `CCNOT` işleminin uygulanması için kaç `T` kapısı gerektiğini sayalım. 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>Bir C# program Içinde temel işlem sayacını kullanma

`CCNOT`, gerçekten 7 `T` kapısı gerektirdiğini ve `CCNOTDriver` 8 `T` kapıları yürüttüğünü denetlemek için aşağıdaki C# kodu kullanabiliriz:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

Programın ilk kısmı `CCNOTDriver`yürütür. İkinci bölümde, `CCNOTDriver`tarafından yürütülen T kapıları sayısını almak için yöntemi `QCTraceSimulator.GetMetric` kullanırız: 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

`GetMetric` iki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür. Örnek işlem `Primitive.CCNOT` `CCNOTDriver` içinde çağrılır ve bu nedenle çağrı grafı Edge `<Primitive.CCNOT,CCNOTDriver>`içerir. 

Kullanılan `CNOT` kapıları sayısını almak için aşağıdaki satırı ekleyebiliriz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
