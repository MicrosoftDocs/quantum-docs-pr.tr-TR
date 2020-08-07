---
title: Genişlik sayacı-hisse geliştirme seti
description: Bir programdaki işlemler tarafından ayrılan ve ödünç alınan qubits sayısını saymak için hisse izi simülatörü kullanan Microsoft QDK genişlik sayacı hakkında bilgi edinin Q# .
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868211"
---
# <a name="quantum-trace-simulator-width-counter"></a>Hisse izleme simülatörü: Genişlik sayacı

Genişlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Bu işlemi, bir programdaki her bir işlem tarafından ayrılan ve ödünç alınan qubits sayısını saymak için kullanabilirsiniz Q# . Bazı temel işlemler ek qubit ayırabilir, örneğin, denetlenen `X` işlemleri veya denetlenen işlemleri de çarpır `T` .

## <a name="invoking-the-width-counter"></a>Genişlik sayacını çağırma

Hisse izi izleme simülatörünü Width sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliği true olarak ayarlamanız `UseWidthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` . 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>C# ana programında Width sayacını kullanma

Bu bölümde aşağıdaki C# örneği, <xref:microsoft.quantum.intrinsic.x> Aşağıdaki örnek koda bağlı olarak, çarpma denetimli bir işlemin uygulanmasıyla ayrılan ek qubits sayısını hesaplar Q# :

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

Çarpma kontrollü <xref:microsoft.quantum.intrinsic.x> işlemi, toplam beş qubit üzerinde çalışır, iki [anyaya bitleri](xref:microsoft.quantum.glossary#ancilla)ayırır ve bir giriş genişliğine **5**sahiptir. Sayıları doğrulamak için aşağıdaki C# programını kullanın:

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

Programın ilk kısmı `ApplyMultiControlledX` işlemi çalıştırır. İkinci bölüm, [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ayrılan qubits sayısını ve `Controlled X` işlemin girdi olarak aldığı qubit sayısını almak için yöntemini kullanır. 

Son olarak, aşağıdaki şekilde, Genişlik sayacı tarafından toplanan tüm istatistiklerin CSV biçiminde çıktısını alabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>Ayrıca bkz.

- Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API başvurusu.
