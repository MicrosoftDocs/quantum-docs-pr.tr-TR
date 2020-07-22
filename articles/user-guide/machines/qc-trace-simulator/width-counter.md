---
title: Genişlik sayacı-hisse geliştirme seti
description: 'Bir Q # programındaki işlemlere ayrılan ve ödünç alınan qubits sayısını saymak için hisse izi simülatörü kullanan Microsoft QDK genişlik sayacı hakkında bilgi edinin.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871543"
---
# <a name="quantum-trace-simulator-width-counter"></a>Hisse izleme simülatörü: Genişlik sayacı

Genişlik sayacı, hisse Geliştirme Seti [hisse izleyici benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Bu özelliği, bir Q # programındaki her işlem tarafından ayrılan ve ödünç alınan qubits sayısını saymak için kullanabilirsiniz. Bazı temel işlemler ek qubit ayırabilir, örneğin, denetlenen `X` işlemleri veya denetlenen işlemleri de çarpır `T` .

## <a name="invoking-the-width-counter"></a>Genişlik sayacını çağırma

Hisse izi izleme simülatörünü Width sayacından çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliği true olarak ayarlamanız `UseWidthCounter` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` . 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>C# ana programında Width sayacını kullanma

Bu bölümde aşağıdaki C# örneği, <xref:microsoft.quantum.intrinsic.x> aşağıdaki Q # örnek koduna bağlı olarak, çarpma denetimli bir işlemin uygulanmasıyla ayrılan ekstra qubits sayısını hesaplar:

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
