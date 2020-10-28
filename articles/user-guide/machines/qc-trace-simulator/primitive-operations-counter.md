---
title: Temel işlem sayacı-hisse geliştirme seti
description: Bir programdaki işlemler tarafından kullanılan temel işlemleri izlemek için hisse izi simülatörü kullanan Microsoft QDK temel işlem sayacı hakkında bilgi edinin Q# .
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690946"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>Hisse izleme simülatörü: temel işlemler sayacı

Temel işlem sayacı, hisse Geliştirme Seti [hisse izleme benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Bir hisse bir programda çağrılan her işlem tarafından kullanılan temel işlem sayısını sayar. 

Tüm <xref:Microsoft.Quantum.Intrinsic> işlemler tek qubit döndürmeler, T işlemleri, tek qubit Clienfford işlemleri, CNOT işlemleri ve Multi-Qubitpauli gözlemlenenler ölçümleri bakımından ifade edilir. Temel Işlem sayacı, işlemin [çağrı grafiğinin](https://en.wikipedia.org/wiki/Call_graph)tüm kenarlarına ilişkin istatistikleri toplar ve toplar.

## <a name="invoking-the-primitive-operation-counter"></a>Temel işlem sayacını çağırma

Temel işlem sayacı ile hisse izi simülatörü çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, `UsePrimitiveOperationsCounter` özelliği **true** olarak ayarlamanız ve sonra <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak ile yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>C# ana programında temel işlem sayacını kullanma

<xref:Microsoft.Quantum.Intrinsic.T> <xref:Microsoft.Quantum.Intrinsic.ccnot> Aşağıdaki örnek koda bağlı olarak, bu bölümde aşağıdaki C# örneği, işlemi uygulamak için kaç işlem gerektiğini sayar Q# :

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

Bunun `CCNOT` yedi `T` işlem gerektirdiğini ve `ApplySampleWithCCNOT` sekiz işlem çalıştırmasını denetlemek Için `T` Aşağıdaki C# kodunu kullanın:

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

Programın ilk kısmı çalışır `ApplySampleWithCCNOT` . İkinci bölüm, [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) tarafından çalıştırılan işlem sayısını almak için yöntemini kullanır `T` `ApplySampleWithCCNOT` : 

`GetMetric`İki tür parametresiyle çağırdığınızda, belirli bir çağrı grafiği kenarıyla ilişkili ölçüm değerini döndürür. Önceki örnekte program `Primitive.CCNOT` içindeki işlemi çağırır `ApplySampleWithCCNOT` ve bu nedenle çağrı grafı kenarı içerir `<Primitive.CCNOT, ApplySampleWithCCNOT>` . 

Kullanılan işlem sayısını almak için `CNOT` aşağıdaki satırı ekleyin:
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

Son olarak, aşağıdakiler kullanılarak CSV biçiminde Temel Işlemler sayacı tarafından toplanan tüm istatistiklerin çıktısını alabilirsiniz:
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>Ayrıca bkz.

- Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API başvurusu.