---
title: Ayrı girişler denetleyicisi-hisse geliştirme seti
description: 'Paylaşılan qubits ile olası çakışmalar için Q # kodunuzu denetlemek üzere hisse izleme simülatörünü kullanan Microsoft QDK farklı giriş denetleyicisi hakkında bilgi edinin.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871153"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>Hisse izleme simülatörü: ayrı girişler denetleyicisi

Ayrı giriş denetleyicisi, hisse Geliştirme Seti [hisse izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nın bir parçasıdır. Paylaşılan qubits ile çakışmalar nedeniyle oluşan koddaki olası hataları tespit etmek için bunu kullanabilirsiniz. 

## <a name="conflicts-with-shared-qubits"></a>Paylaşılan qubits ile çakışmalar

Ayrı giriş denetleyicisi tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun:

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

Bu programa baktığımızda, ve `op1` `op2` `q1` `q2` farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğu için, hangi sıranın çağrı yaptığı ve bunu fark etmemiş olduğunu varsayabilirsiniz. 

Şu anda bu örneği göz önünde bulundurun:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

`op1`Ve `op2` öğelerinin her ikisi de kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşır. `ApplyBoth`Bu örnekte çağırdığınızda, işlemin sonucu, `op1` `op2` `ApplyBoth` oluşmasını beklediğiniz şekilde değil, bu sıraya bağlıdır. Ayrı giriş denetleyicisini etkinleştirdiğinizde bu durum söz konusu durumları algılar ve bir oluşturur `DistinctInputsCheckerException` . Daha fazla bilgi için, bkz <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> . Q # API kitaplığı.

## <a name="invoking-the-distinct-inputs-checker"></a>Ayrı giriş denetleyicisini çağırma

Farklı giriş denetleyicisi ile hisse izleme simülatörünü çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliği true olarak ayarlamanız `UseDistinctInputsChecker` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` . 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>C# konak programında ayrı giriş denetleyicisi 'ni kullanma

Aşağıda ayrı girişler denetleyicisi etkin olan hisse izi simülatörü kullanan C# ana bilgisayar programı örneği verilmiştir:

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>Ayrıca bkz.

- Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API başvurusu.
