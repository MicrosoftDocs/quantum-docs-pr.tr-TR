---
title: Hisse kaynakları tahmin aracı-hisse geliştirme seti
description: Bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden Microsoft QDK kaynakları Estimator hakkında bilgi edinin Q# .
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1892431c3e332385a5bcefa357eb64a9fac3f381
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992250"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="de3b4-103">Hisse geliştirme seti (QDK) kaynakları tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="de3b4-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="de3b4-104">Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı Q# bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="de3b4-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="de3b4-105">Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, Q# kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan işlemler için kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="de3b4-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="de3b4-106">Kaynaklar, hata ayıklama programlarında yardımcı olacak daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="de3b4-107">Kaynak tahmin aracı 'ı çağırma ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="de3b4-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="de3b4-108">Herhangi bir işlemi çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="de3b4-109">Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="de3b4-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="de3b4-110">C 'den kaynak tahmin aracı çağrılıyor #</span><span class="sxs-lookup"><span data-stu-id="de3b4-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="de3b4-111">Diğer hedef makinelerde olduğu gibi, önce `ResourceEstimator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="de3b4-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="de3b4-112">`QuantumSimulator` sınıfının aksine, `ResourceEstimator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="de3b4-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="de3b4-113">Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` sekmeyle ayrılmış değerler (TSV) içeren bir tablo üreten yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="de3b4-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="de3b4-114">Tabloyu bir dosyaya kaydedebilir veya analiz için konsolda görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="de3b4-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="de3b4-115">Aşağıda, önceki programın örnek bir çıktısı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="de3b4-115">The following is a sample output from the preceding program:</span></span>

```output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="de3b4-116">`ResourcesEstimator`Örnek, her çalıştırmada hesaplamalarını sıfırlamaz.</span><span class="sxs-lookup"><span data-stu-id="de3b4-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="de3b4-117">Başka bir işlem çalıştırmak için aynı örneği kullanırsanız, yeni sonuçları mevcut sonuçlarla toplar.</span><span class="sxs-lookup"><span data-stu-id="de3b4-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="de3b4-118">Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her çalıştırma için yeni bir örnek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="de3b4-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="de3b4-119">Python 'dan kaynak tahmin aracı çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="de3b4-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="de3b4-120">Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan Q# işlemle kullanın:</span><span class="sxs-lookup"><span data-stu-id="de3b4-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="de3b4-121">Kaynak tahmin aracı 'ı komut satırından çağırma</span><span class="sxs-lookup"><span data-stu-id="de3b4-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="de3b4-122">Q#Komut satırından bir program çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="de3b4-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="de3b4-123">Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="de3b4-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="de3b4-124">Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma</span><span class="sxs-lookup"><span data-stu-id="de3b4-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="de3b4-125">Q#İşlemi çalıştırmak için I Magic komutunu [% Tahmini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="de3b4-126">Tahmini verileri program aracılığıyla alma</span><span class="sxs-lookup"><span data-stu-id="de3b4-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="de3b4-127">TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` .</span><span class="sxs-lookup"><span data-stu-id="de3b4-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="de3b4-128">`Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.</span><span class="sxs-lookup"><span data-stu-id="de3b4-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="de3b4-129">Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir işlem tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir Q# :</span><span class="sxs-lookup"><span data-stu-id="de3b4-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="de3b4-130">Bildirilen ölçümler</span><span class="sxs-lookup"><span data-stu-id="de3b4-130">Metrics Reported</span></span>

<span data-ttu-id="de3b4-131">Tahmin aracı kaynakları aşağıdaki ölçümleri izler:</span><span class="sxs-lookup"><span data-stu-id="de3b4-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="de3b4-132">Ölçüm</span><span class="sxs-lookup"><span data-stu-id="de3b4-132">Metric</span></span>|<span data-ttu-id="de3b4-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="de3b4-133">Description</span></span>|
|----|----|
|<span data-ttu-id="de3b4-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="de3b4-134">__CNOT__</span></span>    |<span data-ttu-id="de3b4-135">İşlemlerin çalıştırma sayısı `CNOT` (denetlenen Pauli X işlemleri olarak da bilinir).</span><span class="sxs-lookup"><span data-stu-id="de3b4-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="de3b4-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="de3b4-136">__QubitClifford__</span></span> |<span data-ttu-id="de3b4-137">Herhangi bir tek qubit Clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="de3b4-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="de3b4-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="de3b4-138">__Measure__</span></span>    |<span data-ttu-id="de3b4-139">Ölçümlerin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="de3b4-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="de3b4-140">__R__</span><span class="sxs-lookup"><span data-stu-id="de3b4-140">__R__</span></span>    |<span data-ttu-id="de3b4-141">Tüm tek qubit döndürmeler, hariç tutulan `T` , clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="de3b4-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="de3b4-142">__T__</span><span class="sxs-lookup"><span data-stu-id="de3b4-142">__T__</span></span>    |<span data-ttu-id="de3b4-143">İşlemler `T` `T` , T_x = H. T. H ve T_y = HY. t. HY dahil olmak üzere işlemlerin ve bunların Birleşik kapılarının çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="de3b4-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="de3b4-144">__Derinliğini__</span><span class="sxs-lookup"><span data-stu-id="de3b4-144">__Depth__</span></span>|<span data-ttu-id="de3b4-145">İşlem tarafından çalıştırılan hisse devdevlik derinliğine yönelik alt sınır Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="de3b4-146">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="de3b4-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="de3b4-147">Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="de3b4-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="de3b4-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="de3b4-148">__Width__</span></span>    |<span data-ttu-id="de3b4-149">İşlemin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="de3b4-150">Aynı anda hem __derinlik__ hem de __Genişlik__ alt sınırlarına ulaşmak mümkün olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="de3b4-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="de3b4-151">__Borrodilimlerin genişliği__</span><span class="sxs-lookup"><span data-stu-id="de3b4-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="de3b4-152">İşlem içinde ödünç alınan en fazla qubits sayısı Q# .</span><span class="sxs-lookup"><span data-stu-id="de3b4-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="de3b4-153">Ölçüm sonuçlarının olasılığını sağlama</span><span class="sxs-lookup"><span data-stu-id="de3b4-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="de3b4-154"><xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="de3b4-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="de3b4-155">Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="de3b4-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="de3b4-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="de3b4-156">See also</span></span>

- [<span data-ttu-id="de3b4-157">Hisse izi izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="de3b4-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="de3b4-158">Kuantum Toffoli simülatörü</span><span class="sxs-lookup"><span data-stu-id="de3b4-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="de3b4-159">Kuantum tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="de3b4-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 