---
title: Geçersiz kılınan kubit kullanımı denetleyicisi
description: 'Microsoft QDK geçersiz kılınan qubits kullanım denetleyicisi hakkında bilgi edinin. Bu, olası geçersiz qubits için Q # kodunuzu denetler.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275568"
---
# <a name="invalidated-qubits-use-checker"></a>Geçersiz kılınan qubits kullanımı denetleyicisi

, `Invalidated Qubits Use Checker` Koddaki olası hataları algılamak için tasarlanan hisse bilgisayar [izlenebenzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro) bir parçasıdır. Tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun `Invalidated Qubits Use Checker` .

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

`H`Öğesine uygulandığında, `q[0]` zaten yayınlanmış bir qubit 'e işaret eder. Bu tanımsız davranışa neden olabilir. `Invalidated Qubits Use Checker`Etkinleştirildiğinde, `InvalidatedQubitsUseCheckerException` zaten yayımlanmış bir qubit 'e bir işlem uygulanırsa özel durum oluşturulur. Daha fazla bilgi için [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) adresindeki API belgelerine bakın.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>C# programınızda geçersiz qubits kullanım denetleyicisi 'Ni kullanma

Aşağıda, hisse bilgisayarı etkin bir şekilde kullanmaya yönelik C# sürücü kodu örneği verilmiştir `Trace
Simulator` `Invalidated Qubits Use Checker` : 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

Sınıfı, `QCTraceSimulatorConfiguration` hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve Oluşturucu için bir bağımsız değişken olarak bulunabilir `QCTraceSimulator` . `useInvalidatedQubitsUseChecker`True olarak ayarlandığında, `Invalidated Qubits Use Checker` etkindir. Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) hakkında API belgeleri.

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
