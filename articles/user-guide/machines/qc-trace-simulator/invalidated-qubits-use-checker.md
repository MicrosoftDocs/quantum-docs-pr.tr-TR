---
title: Geçersiz kılınan qubits denetleyici-hisse geliştirme seti
description: Q#Büyük olasılıkla geçersiz qubits için kodunuzu denetlemek üzere hisse izi simülatörü kullanan Microsoft QDK geçersiz kılınan qubits kullanım denetleyicisi hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868296"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>Hisse izleme simülatörü: geçersiz qubits kullanım denetleyicisi

Geçersiz kılınan qubits kullanım denetleyicisi, hisse Geliştirme Seti [hisse izleme benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Geçersiz qubits nedeniyle oluşan koddaki olası hataları tespit etmek için bunu kullanabilirsiniz. 

## <a name="invalid-qubits"></a>Geçersiz qubits

Q#Geçersiz kılınan qubits kullanım denetleyicisi tarafından algılanan sorunları göstermek için aşağıdaki kod parçasını göz önünde bulundurun:

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

`H`İşlemi uygulamasına uyguladığınızda `q[0]` , önceden yayımlanmış bir qubit 'e işaret eder ve bu, tanımsız davranışa neden olabilir. Geçersiz kılınan qubits kullanım denetleyicisi etkinleştirildiğinde, `InvalidatedQubitsUseCheckerException` Program zaten yayınlanmış bir qubit 'e bir işlem uygularsa özel durumu oluşturur. Daha fazla bilgi için bkz. <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.

## <a name="invoking-the-invalidated-qubits-use-checker"></a>Geçersiz kılınan qubits kullanım denetleyicisi çağrılıyor

Geçersiz kılınan qubits kullanım denetleyicisi ile hisse izleme simülatörünü çalıştırmak için bir örnek oluşturmanız <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> , `UseInvalidatedQubitsUseChecker` özelliği **true**olarak ayarlamanız ve sonra <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` . 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>C# ana programında geçersiz kılınan qubits kullanım denetleyicisini kullanma

Aşağıda, geçersiz kılınan qubits kullanım denetleyicisi etkin olan hisse izi simülatörü kullanan C# konak programlarının bir örneği verilmiştir: 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
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
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API başvurusu.