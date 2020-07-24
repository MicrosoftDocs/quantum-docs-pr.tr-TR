---
title: Kuantum izleme simülatörü - Quantum geliştirme seti
description: Klasik kodda hata ayıklamak ve bir Q# programının kaynak gereksinimlerini tahmin etmek için Microsoft kuantum bilgisayarı izleme simülatörünü nasıl kullanacağınızı öğrenin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871119"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Microsoft Quantum geliştirme seti (QDK) kuantum izleme simülatörü

QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> sınıfı, bir kuantum bilgisayarı durumunun gerçekten simülasyonunu yapmadan kuantum programı çalıştırır. Bu nedenle, kuantum izleme simülatörü binlerce kubit kullanan kuantum programlarını çalıştırabilir.  İki ana amaç için yararlıdır: 

* Kuantum programının parçası olan klasik kodun hatalarını ayıklamak. 
* Kuantum programının belirli bir örneğini bir kuantum bilgisayarında çalıştırmak için gereken kaynakları tahmin etmek. Dahası, çok daha sınırlı bir ölçüm kümesi sağlayan [Kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator), izleme simülatörünü temel almıştır.

## <a name="invoking-the-quantum-trace-simulator"></a>Kuantum izleme simülatörünü çağırma

Tüm Q# işlemlerini çalıştırmak için kuantum izleme simülatörünü kullanabilirsiniz.

Diğer hedef makinelerde olduğu gibi, önce `QCTraceSimulator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.

`QuantumSimulator` sınıfının aksine, `QCTraceSimulator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm sonuçlarının olasılığını sağlama

Kuantum izleme simülatörü gerçek kuantum durumunun simülasyonunu yapmadığından, işlem içindeki ölçüm sonuçlarının olasılığını hesaplayamaz. 

Bu nedenle, bir işlem ölçüm içeriyorsa, <xref:microsoft.quantum.diagnostics> ad alanındaki <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> işlemini kullanarak bu olasılıkları açıkça sağlamanız gerekir. Aşağıdaki örnekte bu gösterilmektedir:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

Kuantum izleme simülatörü `AssertMeasurementProbability` ile karşılaştığında, bu `PauliZ` ölçümünü `source` üzerine kaydeder ve `q`, **0,5** olasılıkla `Zero` sonucunu vermelidir. Daha sonra `M` işlemini çalıştırdığında, sonuç olasılıklarının kayıtlı değerlerini bulur ve `M`, **0,5** olasılıkla `Zero` veya `One` döndürür. Aynı kod, kuantum durumunu takip eden bir simülatör üzerinde çalıştırıldığında, bu simülatör `AssertMeasurementProbability` içinde belirtilen olasılıkların doğru olup olmadığını kontrol eder.

`AssertMeasurementProbability` kullanılarak not eklenmemiş en az bir ölçüm işlemi varsa, simülatörün [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) sonucunu verdiğini unutmayın.

## <a name="quantum-trace-simulator-tools"></a>Kuantum izleme simülatörü araçları

QDK, programlarınızda hata algılamak ve kuantum programı kaynak tahminleri gerçekleştirmek için kuantum izleme simülatörü ile kullanabileceğiniz beş araç içerir: 

|Araç | Açıklama |
|-----| -----|
|[Ayrı giriş denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |Paylaşılan kubitlerle olası çakışmaları denetler |
|[Geçersiz kılınan kubit kullanımı denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |Programın zaten yayınlanmış olan bir kubite işlem uygulayıp uygulamadığını denetler |
|[Temel işlem sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | Kuantum programında çağrılan her işlem tarafından kullanılan temel yürütme sayısını verir  |
|[Derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |Kuantum programında çağrılan her işlemin derinlik alt sınırını temsil eden sayıları toplar   |
|[Genişlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |Kuantum programında her işlem tarafından ayrılan ve ödünç alınan kubit sayısını verir |

Bu araçların her biri, `QCTraceSimulatorConfiguration` içinde uygun bayrakların ayarlanması ve sonra yapılandırmanın `QCTraceSimulator` bildirimine geçirilmesiyle etkinleştirilir. Bu araçların her birini kullanmayla ilgili daha fazla bilgi için önceki listede yer alan bağlantılara bakın. `QCTraceSimulator` yapılandırması hakkında daha fazla bilgi için bkz. [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).

## <a name="qctracesimulator-methods"></a>QCTraceSimulator metotları

`QCTraceSimulator`, bir kuantum işlemi sırasında izlenen ölçümlerin değerlerini almak için birkaç yerleşik metot içerir. [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) ve [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) metodu örnekleri, [Temel işlem sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) ve [Genişlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) makalelerinde bulunabilir. Kullanılabilir tüm metotlar hakkında daha fazla bilgi için, Q# API başvurusundaki [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) konusuna bakın.  

## <a name="see-also"></a>Ayrıca bkz.

- [Kuantum kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator)
- [Kuantum Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kuantum tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) 