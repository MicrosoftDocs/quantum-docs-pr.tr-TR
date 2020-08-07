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
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="4259a-103">Hisse izleme simülatörü: geçersiz qubits kullanım denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="4259a-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="4259a-104">Geçersiz kılınan qubits kullanım denetleyicisi, hisse Geliştirme Seti [hisse izleme benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="4259a-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="4259a-105">Geçersiz qubits nedeniyle oluşan koddaki olası hataları tespit etmek için bunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4259a-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="4259a-106">Geçersiz qubits</span><span class="sxs-lookup"><span data-stu-id="4259a-106">Invalid qubits</span></span>

<span data-ttu-id="4259a-107">Q#Geçersiz kılınan qubits kullanım denetleyicisi tarafından algılanan sorunları göstermek için aşağıdaki kod parçasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="4259a-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="4259a-108">`H`İşlemi uygulamasına uyguladığınızda `q[0]` , önceden yayımlanmış bir qubit 'e işaret eder ve bu, tanımsız davranışa neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="4259a-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="4259a-109">Geçersiz kılınan qubits kullanım denetleyicisi etkinleştirildiğinde, `InvalidatedQubitsUseCheckerException` Program zaten yayınlanmış bir qubit 'e bir işlem uygularsa özel durumu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4259a-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="4259a-110">Daha fazla bilgi için bkz. <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span><span class="sxs-lookup"><span data-stu-id="4259a-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="4259a-111">Geçersiz kılınan qubits kullanım denetleyicisi çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="4259a-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="4259a-112">Geçersiz kılınan qubits kullanım denetleyicisi ile hisse izleme simülatörünü çalıştırmak için bir örnek oluşturmanız <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> , `UseInvalidatedQubitsUseChecker` özelliği **true**olarak ayarlamanız ve sonra <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="4259a-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="4259a-113">C# ana programında geçersiz kılınan qubits kullanım denetleyicisini kullanma</span><span class="sxs-lookup"><span data-stu-id="4259a-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="4259a-114">Aşağıda, geçersiz kılınan qubits kullanım denetleyicisi etkin olan hisse izi simülatörü kullanan C# konak programlarının bir örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="4259a-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="4259a-115">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="4259a-115">See also</span></span>

- <span data-ttu-id="4259a-116">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="4259a-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="4259a-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="4259a-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="4259a-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="4259a-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="4259a-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="4259a-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>