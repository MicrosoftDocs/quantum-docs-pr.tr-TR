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
# <a name="distinct-inputs-checker"></a><span data-ttu-id="fe50f-103">Ayrı girişler denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="fe50f-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="fe50f-104">, `Distinct Inputs Checker` Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)'nin bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="fe50f-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="fe50f-105">Koddaki olası hataları algılamak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fe50f-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="fe50f-106">Bu paket tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="fe50f-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="fe50f-107">Kullanıcı bu programa baktığı zaman, `op1` ve `op2` olarak çağrılan sıranın farklı qugeler `q1` `q2` ve farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="fe50f-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="fe50f-108">Şimdi bu işlemin kullanıldığı bir örneği düşünmemize izin verin:</span><span class="sxs-lookup"><span data-stu-id="fe50f-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="fe50f-109">Şimdi `op1` ve `op2` kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşırlar.</span><span class="sxs-lookup"><span data-stu-id="fe50f-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="fe50f-110">Kullanıcı, yukarıdaki örneğe çağrı yaptığı zaman, `ApplyBoth` işlem sonucu ve içindeki sırasına göre değişir `op1` `op2` `ApplyBoth` .</span><span class="sxs-lookup"><span data-stu-id="fe50f-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="fe50f-111">Bu, kullanıcının gerçekleşmesi beklenmez.</span><span class="sxs-lookup"><span data-stu-id="fe50f-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="fe50f-112">`Distinct Inputs Checker`Etkinleştirildiğinde bu tür durumları tespit eder ve oluşturulur `DistinctInputsCheckerException` .</span><span class="sxs-lookup"><span data-stu-id="fe50f-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="fe50f-113">Daha fazla bilgi için [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) adresindeki API belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="fe50f-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="fe50f-114">C# programınızda ayrı giriş denetleyicisi 'Ni kullanma</span><span class="sxs-lookup"><span data-stu-id="fe50f-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="fe50f-115">Aşağıda, Lem bilgisayar izleme simülatörü etkin ile kullanmak için C# sürücü kodunun bir örneği verilmiştir `Distinct Inputs Checker` :</span><span class="sxs-lookup"><span data-stu-id="fe50f-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="fe50f-116">Sınıfı, `QCTraceSimulatorConfiguration` hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve Oluşturucu için bir bağımsız değişken olarak bulunabilir `QCTraceSimulator` .</span><span class="sxs-lookup"><span data-stu-id="fe50f-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="fe50f-117">`useDistinctInputsChecker`True olarak ayarlandığında, `Distinct Inputs Checker` etkindir.</span><span class="sxs-lookup"><span data-stu-id="fe50f-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="fe50f-118">Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) hakkında API belgeleri.</span><span class="sxs-lookup"><span data-stu-id="fe50f-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe50f-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="fe50f-119">See also</span></span>

- <span data-ttu-id="fe50f-120">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="fe50f-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
