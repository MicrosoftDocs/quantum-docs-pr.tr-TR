---
title: Temel Işlem sayacı
description: Bir hisse bir programdaki işlemler tarafından kullanılan temel yürütmelerin sayısını izleyen Microsoft QDK temel Işlem sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275552"
---
# <a name="primitive-operations-counter"></a>Temel Işlem sayacı  

, `Primitive Operations Counter` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır. Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel yürütme sayısını sayar. ' Den tüm işlemler `Microsoft.Quantum.Intrinsic` tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Toplanan istatistikler, işlemler çağrı grafiğinin kenarları üzerinden toplanır. Şimdi `T` , işlemi uygulamak için kaç kapı olduğunu saymamıza izin verin `CCNOT` . 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>C# programı içinde temel Işlem sayacını kullanma

`CCNOT`Gerçekten 7 kapı gerektirip gerektirmediğini ve 8 kapıları çalıştıran bir denetim için `T` `ApplySampleWithCCNOT` `T` Aşağıdaki C# kodunu kullanabiliriz:

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

Programın ilk kısmı yürütülür `ApplySampleWithCCNOT` . İkinci bölümde, `QCTraceSimulator.GetMetric` tarafından yürütülen T kapıları sayısını almak için yöntemini kullanıyoruz `ApplySampleWithCCNOT` : 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

`GetMetric`İki tür parametresiyle çağrıldığında, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür. Örnek işlem `Primitive.CCNOT` içinde çağrılır `ApplySampleWithCCNOT` ve bu nedenle çağrı grafı kenarı içerir `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Kullanılan kapı sayısını almak için `CNOT` aşağıdaki satırı ekleyebiliriz:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Son olarak, ağ geçidi sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için şunları kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
