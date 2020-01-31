---
title: Farklı giriş denetleyicisi | Hisse bilgisayar izleme simülatörü | Microsoft Docs
description: Kuantum bilgisayar izleme simülatörüne genel bakış
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820972"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="9b7ad-103">Ayrı girişler denetleyicisi</span><span class="sxs-lookup"><span data-stu-id="9b7ad-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="9b7ad-104">`Distinct Inputs Checker`, hisse bilgisayar [Izleme Benzeticisinin](xref:microsoft.quantum.machines.qc-trace-simulator.intro)bir parçasıdır.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="9b7ad-105">Koddaki olası hataları algılamak için tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="9b7ad-106">Bu paket tarafından algılanan sorunları göstermek için aşağıdaki Q # kodu parçasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="9b7ad-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="9b7ad-107">Kullanıcı bu programa baktığı zaman, `q1` ve `q2` farklı qugeler ve farklı qubits commute üzerinde çalışan farklı qubit ve işlemler olduğundan, `op1` ve `op2` olarak çağrılan sıranın önemi yoktur.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="9b7ad-108">Şimdi bu işlemin kullanıldığı bir örneği düşünmemize izin verin:</span><span class="sxs-lookup"><span data-stu-id="9b7ad-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="9b7ad-109">Artık `op1` ve `op2` her ikisi de kısmi uygulama kullanılarak elde edilir ve bir qubit paylaşır.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="9b7ad-110">Kullanıcı, yukarıdaki örnekte `ApplyBoth` çağırdığında, işlemin sonucu, `ApplyBoth`içindeki `op1` ve `op2` sırasına göre değişir.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="9b7ad-111">Bu, kullanıcının gerçekleşmesi beklenmez.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="9b7ad-112">`Distinct Inputs Checker`, etkinleştirildiğinde bu durumları tespit eder ve `DistinctInputsCheckerException`oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="9b7ad-113">Daha fazla bilgi için [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) adresindeki API belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="9b7ad-114">C# Programınızda ayrı giriş denetleyicisi 'ni kullanma</span><span class="sxs-lookup"><span data-stu-id="9b7ad-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="9b7ad-115">Aşağıda, `Distinct Inputs Checker` etkinken hisse bilgisayar C# izleme simülatörü kullanmaya yönelik bir sürücü kodu örneği verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="9b7ad-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="9b7ad-116">`QCTraceSimulatorConfiguration` sınıfı, hisse bilgisayar izleme simülatörü yapılandırmasını depolar ve `QCTraceSimulator` Oluşturucu için bir bağımsız değişken olarak temin edilebilir.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="9b7ad-117">`useDistinctInputsChecker` true olarak ayarlandığında `Distinct Inputs Checker` etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="9b7ad-118">Daha fazla bilgi için bkz. [Qctracesimülatör](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) ve [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) hakkında API belgeleri.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b7ad-119">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-119">See also</span></span>

- <span data-ttu-id="9b7ad-120">Hisse bilgisayar [Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) genel bakış.</span><span class="sxs-lookup"><span data-stu-id="9b7ad-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
