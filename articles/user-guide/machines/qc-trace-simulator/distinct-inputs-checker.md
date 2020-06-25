---
title: Ayrı girişler denetleyicisi
description: 'Microsoft QDK farklı giriş denetleyicisi hakkında bilgi edinin. Bu, paylaşılan qubits ile olası çakışmalar için Q # kodunuzu denetler.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275616"
---
# <a name="distinct-inputs-checker"></a>Ayrı girişler denetleyicisi

, `Distinct Inputs Checker` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır. Koddaki olası hataları algılamak için tasarlanmıştır. Bu paket tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun:

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

Kullanıcı bu programa baktığı zaman, `op1` ve `op2` olarak çağrılan sıranın farklı qugeler `q1` `q2` ve farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğu anlamına gelir. Şimdi bu işlemin kullanıldığı bir örneği düşünmemize izin verin:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Şimdi `op1` ve `op2` kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşırlar. Kullanıcı, yukarıdaki örneğe çağrı yaptığı zaman, `ApplyBoth` işlem sonucu ve içindeki sırasına göre değişir `op1` `op2` `ApplyBoth` . Bu, kullanıcının gerçekleşmesi beklenmez. `Distinct Inputs Checker`Etkinleştirildiğinde bu tür durumları tespit eder ve oluşturulur `DistinctInputsCheckerException` . Daha fazla bilgi için [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) adresindeki API belgelerine bakın.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>C# programınızda ayrı giriş denetleyicisi 'Ni kullanma

Aşağıda, Lem bilgisayar izleme simülatörü etkin ile kullanmak için C# sürücü kodunun bir örneği verilmiştir `Distinct Inputs Checker` :

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Sınıfı, `QCTraceSimulatorConfiguration` hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve Oluşturucu için bir bağımsız değişken olarak bulunabilir `QCTraceSimulator` . `useDistinctInputsChecker`True olarak ayarlandığında, `Distinct Inputs Checker` etkindir. Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) hakkında API belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
