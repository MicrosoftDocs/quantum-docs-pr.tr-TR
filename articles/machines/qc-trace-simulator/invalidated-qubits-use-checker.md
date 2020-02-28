---
title: Geçersiz kılınan kubit kullanımı denetleyicisi
description: 'Microsoft QDK geçersiz kılınan qubits kullanım denetleyicisi hakkında bilgi edinin. Bu, olası geçersiz qubits için Q # kodunuzu denetler.'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907078"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="9848c-103">Geçersiz kılınan qubits kullanımı denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="9848c-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="9848c-104">`Invalidated Qubits Use Checker`, koddaki olası hataları algılamak için tasarlanan hisse bilgisayar [Izlenebenzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro) bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="9848c-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="9848c-105">`Invalidated Qubits Use Checker`tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="9848c-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="9848c-106">`H` `q[0]` uygulandığında, zaten yayınlanmış bir qubit 'e işaret eder.</span><span class="sxs-lookup"><span data-stu-id="9848c-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="9848c-107">Bu tanımsız davranışa neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="9848c-107">This can cause undefined behavior.</span></span> <span data-ttu-id="9848c-108">`Invalidated Qubits Use Checker` etkinleştirildiğinde, zaten yayımlanmış bir qubit 'e bir işlem uygulanırsa özel durum `InvalidatedQubitsUseCheckerException` atılır.</span><span class="sxs-lookup"><span data-stu-id="9848c-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="9848c-109">Daha fazla bilgi için [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) adresindeki API belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="9848c-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="9848c-110">C# Programınızda geçersiz kılınan qubits kullanım denetleyicisi 'ni kullanma</span><span class="sxs-lookup"><span data-stu-id="9848c-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="9848c-111">Aşağıda, `Invalidated Qubits Use Checker` etkin olan `Trace
Simulator` C# hisse bilgisayar kullanımı için bir sürücü kodu örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="9848c-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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

<span data-ttu-id="9848c-112">`QCTraceSimulatorConfiguration` sınıfı, hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve `QCTraceSimulator` Oluşturucu için bir bağımsız değişken olarak temin edilebilir.</span><span class="sxs-lookup"><span data-stu-id="9848c-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="9848c-113">`useInvalidatedQubitsUseChecker` true olarak ayarlandığında `Invalidated Qubits Use Checker` etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="9848c-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="9848c-114">Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) hakkında API belgeleri.</span><span class="sxs-lookup"><span data-stu-id="9848c-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="9848c-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9848c-115">See also</span></span> ##

- <span data-ttu-id="9848c-116">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="9848c-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
