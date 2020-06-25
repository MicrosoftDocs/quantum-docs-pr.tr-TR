---
title: Genişlik sayacı
description: Bir hisse içindeki her işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayan Microsoft QDK genişlik sayacı hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275567"
---
# <a name="width-counter"></a>Genişlik sayacı

`Width Counter`Her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını sayar.
Ad alanındaki tüm işlemler `Microsoft.Quantum.Intrinsic` tek qubit ifade, T kapıları, tek qubit Clienfford kapıları, CNOT kapıları ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Temel işlemlerden bazıları ek qubit ayırabilirler. Örneğin, denetlenen `X` kapıları veya denetimli kapıları çarpın `T` . Çarpma kontrollü kapıların uygulanması tarafından ayrılan ekstra qubits sayısını hesaplamıza izin verin `X` :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>Bir C# programı içinde Width sayacını kullanma

`X`Toplam 5 qubit üzerinde işlem denetimli olan çarpmaya 2 anyacal ve giriş genişliği 5 olur. Bu durumun bu olduğunu denetlemek için aşağıdaki C# programını kullanabiliriz:

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

Programın ilk kısmı yürütülür `ApplyMultiControlledX` . İkinci bölümde, `QCTraceSimulator.GetMetric` ayrılan qubits sayısını ve denetlenen qubits sayısını ve denetim girişi olarak almak için yöntemini kullanırız `X` . 

Son olarak, Width sayacı tarafından toplanan tüm istatistikleri CSV biçiminde çıkarmak için aşağıdakileri kullanabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
