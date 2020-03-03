---
title: Kuantum bilgisayar izleme simülatörü
description: Klasik kodda hata ayıklamak ve bir kuantum programının kaynak gereksinimlerini tahmin etmek için Microsoft Quantum bilgisayar izleme simülatörünü nasıl kullanacağınızı öğrenin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906092"
---
# <a name="quantum-trace-simulator"></a>Kuantum İzleme Simülatörü

Microsoft kuantum bilgisayarı izleme simülatörü, kuantum bilgisayarın durumunu gerçekten taklit etmeden bir kuantum programı yürütür.  Bu nedenle, izleme simülatörü binlerce kuantum bit kullanan kuantum programlarını çalıştırabilir.  İki ana amaç için yararlıdır: 

* Kuantum programının parçası olan klasik kodun hatalarını ayıklamak. 
* Kuantum programının belirli bir örneğini bir kuantum bilgisayarında çalıştırmak için gereken kaynakları tahmin etmek.

İzleme simülatörü, ölçümlerin gerçekleştirilmesi gerektiğinde kullanıcı tarafından sağlanan ek bilgileri kullanır. Bu konu hakkında daha fazla bilgi için [Ölçüm sonuçlarının olasılığını sağlama](#providing-the-probability-of-measurement-outcomes) bölümüne bakın. 

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm Sonuçlarının Olasılığını Sağlama

Kuantum algoritmalarda görünen iki tür ölçüm vardır. İlk tür, kullanıcının genellikle sonuçların olasılığını bildiği bir yardımcı rol oynar. Bu durumda kullanıcı, bu bilgileri ifade etmek için <xref:microsoft.quantum.intrinsic> ad alanından <xref:microsoft.quantum.intrinsic.assertprob> yazabilir. Aşağıdaki örnekte bu gösterilmektedir:

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

İzleme simülatörü `AssertProb` yürüttüğünde, bu `PauliZ` ölçümünü `source` üzerine kaydeder ve `q` değerine 0,5 olasılıkla `Zero` sonucu verilmelidir. Simülatör daha sonra `M` yürüttüğünde, sonuç olasılıklarının kayıtlı değerlerini bulur ve `M` ölçümü 0,5 olasılıkla `Zero` veya `One` döndürür. Aynı kod, kuantum halini takip eden bir simülatör üzerinde yürütüldüğünde, bu simülatör `AssertProb` içinde belirtilen olasılıkların doğru olup olmadığını kontrol eder.

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>Programınızı Kuantum Bilgisayarı İzleme Simülatörü ile Çalıştırma 

Kuantum bilgisayarı izleme simülatörü başka bir hedef makine olarak görüntülenebilir. Onu kullanmaya yarayan C# sürücü programı ise başka bir kuantum simülatörünün sürücü programına benzer: 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

`AssertProb` kullanılarak not eklenmemiş en az bir ölçüm varsa simülatör `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` ad alanından `UnconstrainedMeasurementException` oluşturur. Daha fazla bilgi için [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) üzerindeki API belgelerine bakın.

Kuantum programlarını çalıştırmaya ek olarak, izleme simülatörü programlardaki hataları algılamaya ve kuantum programı kaynak tahminlerini gerçekleştirmeye yönelik beş bileşen içerir: 

* [Ayrı Giriş Denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Geçersiz Kılınan Kuantum Bit Kullanımı Denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Temel İşlem Sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Devre Derinliği Sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Devre Genişliği Sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

Bu bileşenlerin her biri, `QCTraceSimulatorConfiguration` içinde uygun bayraklar ayarlanarak etkinleştirilebilir. Bu bileşenlerin her birini kullanma hakkında daha ayrıntılı bilgi, ilgili başvuru dosyalarında verilmiştir. Daha ayrıntılı bilgi için [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) üzerindeki API belgelerine bakın.

## <a name="see-also"></a>Ayrıca bkz.
Kuantum bilgisayar [izleme simülatörü](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# başvurusu 

