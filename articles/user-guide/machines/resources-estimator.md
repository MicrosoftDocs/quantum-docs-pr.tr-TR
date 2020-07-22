---
title: Hisse kaynakları tahmin aracı-hisse geliştirme seti
description: 'Bir hisse cığı bilgisayarındaki Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden Microsoft QDK kaynakları Estimator hakkında bilgi edinin.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 0909a050e89d6295664e54ab63cfda5d407a8f12
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870558"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="6b3b2-103">Hisse geliştirme seti (QDK) kaynakları tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="6b3b2-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="6b3b2-104">Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı bir hisse bilgisayar üzerinde Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="6b3b2-105">Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan Q # işlemlerine yönelik kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="6b3b2-106">Tahmin aracı kaynakları, Q # programlarında hata ayıklamaya yardımcı olmak için daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="6b3b2-107">Kaynak tahmin aracı 'ı çağırma ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="6b3b2-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="6b3b2-108">Herhangi bir Q # işlemini çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="6b3b2-109">Daha fazla ayrıntı için bkz. [bir Q # programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="6b3b2-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="6b3b2-110">C 'den kaynak tahmin aracı çağrılıyor #</span><span class="sxs-lookup"><span data-stu-id="6b3b2-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="6b3b2-111">Diğer hedef makinelerde olduğu gibi, önce sınıfının bir örneğini oluşturur `ResourceEstimator` ve sonra bunu bir işlemin yönteminin ilk parametresi olarak iletirsiniz `Run` .</span><span class="sxs-lookup"><span data-stu-id="6b3b2-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="6b3b2-112">Sınıfından farklı olarak, sınıfı `QuantumSimulator` `ResourceEstimator` <xref:System.IDisposable> arabirimini uygulamaz ve bu nedenle onu bir deyime almanız gerekmez `using` .</span><span class="sxs-lookup"><span data-stu-id="6b3b2-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="6b3b2-113">Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` sekmeyle ayrılmış değerler (TSV) içeren bir tablo üreten yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="6b3b2-114">Tabloyu bir dosyaya kaydedebilir veya analiz için konsolda görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="6b3b2-115">Aşağıda, önceki programın örnek bir çıktısı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="6b3b2-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="6b3b2-116">`ResourcesEstimator`Örnek, her çalıştırmada hesaplamalarını sıfırlamaz.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="6b3b2-117">Başka bir işlem çalıştırmak için aynı örneği kullanırsanız, yeni sonuçları mevcut sonuçlarla toplar.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="6b3b2-118">Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her çalıştırma için yeni bir örnek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="6b3b2-119">Python 'dan kaynak tahmin aracı çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="6b3b2-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="6b3b2-120">Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) yöntemini Içeri aktarılan Q # işlemiyle kullanın:</span><span class="sxs-lookup"><span data-stu-id="6b3b2-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="6b3b2-121">Kaynak tahmin aracı 'ı komut satırından çağırma</span><span class="sxs-lookup"><span data-stu-id="6b3b2-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="6b3b2-122">Bir Q # programını komut satırından çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="6b3b2-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="6b3b2-123">Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="6b3b2-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="6b3b2-124">Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma</span><span class="sxs-lookup"><span data-stu-id="6b3b2-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="6b3b2-125">Q # işlemini çalıştırmak için IQ # Magic komutu [% tahminini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="6b3b2-126">Tahmini verileri program aracılığıyla alma</span><span class="sxs-lookup"><span data-stu-id="6b3b2-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="6b3b2-127">TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` .</span><span class="sxs-lookup"><span data-stu-id="6b3b2-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="6b3b2-128">`Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="6b3b2-129">Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir Q # işlemi tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir:</span><span class="sxs-lookup"><span data-stu-id="6b3b2-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="6b3b2-130">Bildirilen ölçümler</span><span class="sxs-lookup"><span data-stu-id="6b3b2-130">Metrics Reported</span></span>

<span data-ttu-id="6b3b2-131">Tahmin aracı kaynakları aşağıdaki ölçümleri izler:</span><span class="sxs-lookup"><span data-stu-id="6b3b2-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="6b3b2-132">Ölçüm</span><span class="sxs-lookup"><span data-stu-id="6b3b2-132">Metric</span></span>|<span data-ttu-id="6b3b2-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6b3b2-133">Description</span></span>|
|----|----|
|<span data-ttu-id="6b3b2-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-134">__CNOT__</span></span>    |<span data-ttu-id="6b3b2-135">İşlemlerin çalıştırma sayısı `CNOT` (denetlenen Pauli X işlemleri olarak da bilinir).</span><span class="sxs-lookup"><span data-stu-id="6b3b2-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="6b3b2-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-136">__QubitClifford__</span></span> |<span data-ttu-id="6b3b2-137">Herhangi bir tek qubit Clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="6b3b2-138">__Measure (Ölçü)__ </span><span class="sxs-lookup"><span data-stu-id="6b3b2-138">__Measure__</span></span>    |<span data-ttu-id="6b3b2-139">Ölçümlerin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="6b3b2-140">__R__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-140">__R__</span></span>    |<span data-ttu-id="6b3b2-141">Tüm tek qubit döndürmeler, hariç tutulan `T` , clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="6b3b2-142">__T__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-142">__T__</span></span>    |<span data-ttu-id="6b3b2-143">İşlemler `T` `T` , T_x = H. T. H ve T_y = HY. t. HY dahil olmak üzere işlemlerin ve bunların Birleşik kapılarının çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="6b3b2-144">__Derinliğini__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-144">__Depth__</span></span>|<span data-ttu-id="6b3b2-145">Q # işlemi tarafından, hisse devdevlik derinliği için alt sınır.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="6b3b2-146">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="6b3b2-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="6b3b2-147">Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="6b3b2-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="6b3b2-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-148">__Width__</span></span>    |<span data-ttu-id="6b3b2-149">Q # işleminin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="6b3b2-150">Aynı anda hem __derinlik__ hem de __Genişlik__ alt sınırlarına ulaşmak mümkün olmayabilir.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="6b3b2-151">__Borrodilimlerin genişliği__</span><span class="sxs-lookup"><span data-stu-id="6b3b2-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="6b3b2-152">Q # işlemi içinde ödünç alınan en fazla qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="6b3b2-153">Ölçüm sonuçları olasılığını sağlama</span><span class="sxs-lookup"><span data-stu-id="6b3b2-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="6b3b2-154"><xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="6b3b2-155">Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="6b3b2-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="6b3b2-156">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="6b3b2-156">See also</span></span>

- [<span data-ttu-id="6b3b2-157">Hisse izi izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="6b3b2-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="6b3b2-158">Hisse Toffoli simülatör</span><span class="sxs-lookup"><span data-stu-id="6b3b2-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="6b3b2-159">Hisse dolu durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="6b3b2-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 