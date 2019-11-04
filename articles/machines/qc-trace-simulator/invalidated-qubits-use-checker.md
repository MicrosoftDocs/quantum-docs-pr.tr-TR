---
title: Geçersiz kılınan qubits kullanım denetleyicisi | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Hisse bilgisayar izleme simülatörünü genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184976"
---
# <a name="invalidated-qubits-use-checker"></a>Geçersiz kılınan qubits kullanımı denetleyicisi

`Invalidated Qubits Use Checker`, koddaki olası hataları algılamak için tasarlanan hisse bilgisayar [Izlenebenzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro) bir parçasıdır. `Invalidated Qubits Use Checker`tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun.

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

`H` `q[0]` uygulandığında, zaten yayınlanmış bir qubit 'e işaret eder. Bu tanımsız davranışa neden olabilir. `Invalidated Qubits Use Checker` etkinleştirildiğinde, zaten yayımlanmış bir qubit 'e bir işlem uygulanırsa özel durum `InvalidatedQubitsUseCheckerException` atılır. Daha fazla bilgi için [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) adresindeki API belgelerine bakın.

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>C# Programınızda geçersiz kılınan qubits kullanım denetleyicisi 'ni kullanma

Aşağıda, `Invalidated Qubits Use Checker` etkin olan `Trace
Simulator` C# hisse bilgisayar kullanımı için bir sürücü kodu örneği verilmiştir: 

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

`QCTraceSimulatorConfiguration` sınıfı, hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve `QCTraceSimulator` Oluşturucu için bir bağımsız değişken olarak temin edilebilir. `useInvalidatedQubitsUseChecker` true olarak ayarlandığında `Invalidated Qubits Use Checker` etkinleştirilir. Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) hakkında API belgeleri.

## <a name="see-also"></a>Ayrıca bkz. ##

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
