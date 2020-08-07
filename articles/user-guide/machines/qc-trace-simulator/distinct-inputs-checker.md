---
title: Ayrı girişler denetleyicisi-hisse geliştirme seti
description: Q#Paylaşılan qubits ile olası çakışmalar için kodunuzu denetlemek üzere hisse izi simülatörünü kullanan Microsoft QDK farklı giriş denetleyicisi hakkında bilgi edinin.
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 750c94e7f861678d37f051619ff5b29bf4fd3d3e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868279"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="03327-103">Hisse izleme simülatörü: ayrı girişler denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="03327-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="03327-104">Ayrı giriş denetleyicisi, hisse Geliştirme Seti [hisse izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nın bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="03327-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="03327-105">Paylaşılan qubits ile çakışmalar nedeniyle oluşan koddaki olası hataları tespit etmek için bunu kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="03327-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="03327-106">Paylaşılan qubits ile çakışmalar</span><span class="sxs-lookup"><span data-stu-id="03327-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="03327-107">Q#Ayrı giriş denetleyicisi tarafından algılanan sorunları göstermek için aşağıdaki kod parçasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="03327-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="03327-108">Bu programa baktığımızda, ve `op1` `op2` `q1` `q2` farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğu için, hangi sıranın çağrı yaptığı ve bunu fark etmemiş olduğunu varsayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="03327-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="03327-109">Şu anda bu örneği göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="03327-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="03327-110">`op1`Ve `op2` öğelerinin her ikisi de kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşır.</span><span class="sxs-lookup"><span data-stu-id="03327-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="03327-111">`ApplyBoth`Bu örnekte çağırdığınızda, işlemin sonucu, `op1` `op2` `ApplyBoth` oluşmasını beklediğiniz şekilde değil, bu sıraya bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="03327-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="03327-112">Ayrı giriş denetleyicisini etkinleştirdiğinizde bu durum söz konusu durumları algılar ve bir oluşturur `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="03327-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="03327-113">Daha fazla bilgi için bkz <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q# . API kitaplığı 'nda.</span><span class="sxs-lookup"><span data-stu-id="03327-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="03327-114">Ayrı giriş denetleyicisini çağırma</span><span class="sxs-lookup"><span data-stu-id="03327-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="03327-115">Farklı giriş denetleyicisi ile hisse izleme simülatörünü çalıştırmak için bir <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> örnek oluşturmanız, özelliği true olarak ayarlamanız `UseDistinctInputsChecker` ve sonra **true** <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> parametresi olarak yeni bir örnek oluşturmanız gerekir `QCTraceSimulatorConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="03327-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="03327-116">C# konak programında ayrı giriş denetleyicisi 'ni kullanma</span><span class="sxs-lookup"><span data-stu-id="03327-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="03327-117">Aşağıda ayrı girişler denetleyicisi etkin olan hisse izi simülatörü kullanan C# ana bilgisayar programı örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="03327-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="03327-118">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="03327-118">See also</span></span>

- <span data-ttu-id="03327-119">Hisse Geliştirme Seti [hisse izi simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="03327-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="03327-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="03327-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="03327-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="03327-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="03327-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API başvurusu.</span><span class="sxs-lookup"><span data-stu-id="03327-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
