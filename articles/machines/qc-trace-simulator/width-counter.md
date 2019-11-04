---
title: Genişlik sayacı | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Hisse bilgisayar izleme simülatörünü genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: e202c527e7e26751361e0c46355ffcefa9c95091
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184925"
---
# <a name="width-counter"></a>Genişlik sayacı

`Width Counter`, her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayar.
`Microsoft.Quantum.Primitive` ad alanındaki tüm işlemler, tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Temel işlemlerden bazıları ek qubit ayırabilirler. Örneğin, denetlenen `X` kapıları veya denetimli `T` kapıları çarpın. Çarpma denetimli bir `X` kapısı uygulamasına göre ayrılan ekstra qubits sayısını hesaplamıza izin verin:

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

# <a name="using-width-counter-within-a-c-program"></a>Bir C# program Içinde Width sayacını kullanma

Toplam 5 qubit üzerinde çalışan denetlenen `X` çarpıp 2 anyacal ve giriş genişliği 5 olur. Bu durumun bu olduğunu denetlemek için aşağıdaki C# programı kullanabiliriz:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

Programın ilk kısmı `MultiControlledXDriver`yürütür. İkinci bölümde, ayrılan qubits sayısını ve denetlenen `X` girdi olarak aldığı qubits sayısını almak için yöntemini `QCTraceSimulator.GetMetric` kullanırız. 

Son olarak, Width sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
