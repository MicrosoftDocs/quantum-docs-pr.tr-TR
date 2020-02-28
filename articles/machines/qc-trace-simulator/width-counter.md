---
title: Genişlik sayacı
description: Bir hisse içindeki her işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayan Microsoft QDK genişlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907095"
---
# <a name="width-counter"></a>Genişlik sayacı

`Width Counter`, her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayar.
`Microsoft.Quantum.Intrinsic` ad alanındaki tüm işlemler, tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Temel işlemlerden bazıları ek qubit ayırabilirler. Örneğin, denetlenen `X` kapıları veya denetimli `T` kapıları çarpın. Çarpma denetimli bir `X` kapısı uygulamasına göre ayrılan ekstra qubits sayısını hesaplamıza izin verin:

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Bir C# program Içinde Width sayacını kullanma

Toplam 5 qubit üzerinde çalışan denetlenen `X` çarpıp 2 anyacal ve giriş genişliği 5 olur. Bu durumun bu olduğunu denetlemek için aşağıdaki C# programı kullanabiliriz:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

Programın ilk kısmı `ApplyMultiControlledX`yürütür. İkinci bölümde, ayrılan qubits sayısını ve denetlenen `X` girdi olarak aldığı qubits sayısını almak için yöntemini `QCTraceSimulator.GetMetric` kullanırız. 

Son olarak, Width sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
