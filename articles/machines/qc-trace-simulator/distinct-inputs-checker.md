---
title: Ayrı girişler denetleyicisi
description: 'Microsoft QDK farklı giriş denetleyicisi hakkında bilgi edinin. Bu, paylaşılan qubits ile olası çakışmalar için Q # kodunuzu denetler.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907112"
---
# <a name="distinct-inputs-checker"></a>Ayrı girişler denetleyicisi

`Distinct Inputs Checker`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır. Koddaki olası hataları algılamak için tasarlanmıştır. Bu paket tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun:

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

Kullanıcı bu programa baktığı zaman, `q1` ve `q2` farklı qugeler ve farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğundan, `op1` ve `op2` olarak çağrılan sıranın önemi yoktur. Şimdi bu işlemin kullanıldığı bir örneği düşünmemize izin verin:

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

Artık `op1` ve `op2` her ikisi de kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşır. Kullanıcı, yukarıdaki örnekte `ApplyBoth` çağırdığında, işlemin sonucu, `ApplyBoth`içindeki `op1` ve `op2` sırasına göre değişir. Bu, kullanıcının gerçekleşmesi beklenmez. `Distinct Inputs Checker`, etkinleştirildiğinde bu durumları tespit eder ve `DistinctInputsCheckerException`oluşturur. Daha fazla bilgi için [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) adresindeki API belgelerine bakın.

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>C# Programınızda ayrı giriş denetleyicisi 'ni kullanma

Aşağıda, `Distinct Inputs Checker` etkinken hisse bilgisayar C# izleme simülatörü kullanmaya yönelik bir sürücü kodu örneği verilmiştir:

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

`QCTraceSimulatorConfiguration` sınıfı, hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve `QCTraceSimulator` Oluşturucu için bir bağımsız değişken olarak temin edilebilir. `useDistinctInputsChecker` true olarak ayarlandığında `Distinct Inputs Checker` etkinleştirilir. Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) hakkında API belgeleri.

## <a name="see-also"></a>Ayrıca bkz.

- Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.
