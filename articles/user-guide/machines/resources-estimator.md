---
title: Hisse kaynakları tahmin aracı-hisse geliştirme seti
description: Bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden Microsoft QDK kaynakları Estimator hakkında bilgi edinin Q# .
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847472"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="b76a2-103">Hisse geliştirme seti (QDK) kaynakları tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="b76a2-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="b76a2-104">Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı Q# bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="b76a2-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="b76a2-105">Bu işlemi, hisse bir bilgisayarın durumunun benzetimini yapmadan hisse, işlem işlemini çalıştırarak gerçekleştirir; Bu nedenle, Q# kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan işlemler için kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="b76a2-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="b76a2-106">Kaynaklar, hata ayıklama programlarında yardımcı olacak daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur Q# .</span><span class="sxs-lookup"><span data-stu-id="b76a2-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="b76a2-107">Kaynak tahmin aracı 'ı çağırma ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="b76a2-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="b76a2-108">Herhangi bir işlemi çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz Q# .</span><span class="sxs-lookup"><span data-stu-id="b76a2-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="b76a2-109">Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="b76a2-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="b76a2-110">C 'den kaynak tahmin aracı çağrılıyor #</span><span class="sxs-lookup"><span data-stu-id="b76a2-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="b76a2-111">Diğer hedef makinelerde olduğu gibi, önce `ResourcesEstimator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="b76a2-112">`QuantumSimulator` sınıfının aksine, `ResourcesEstimator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b76a2-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="b76a2-113">Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` sekmeyle ayrılmış değerler (TSV) içeren bir tablo üreten yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="b76a2-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="b76a2-114">Tabloyu bir dosyaya kaydedebilir veya analiz için konsolda görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="b76a2-115">Aşağıda, önceki programın örnek bir çıktısı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="b76a2-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="b76a2-116">`ResourcesEstimator`Örnek, her çalıştırmada hesaplamalarını sıfırlamaz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="b76a2-117">Başka bir işlem çalıştırmak için aynı örneği kullanırsanız, yeni sonuçları mevcut sonuçlarla toplar.</span><span class="sxs-lookup"><span data-stu-id="b76a2-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="b76a2-118">Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her çalıştırma için yeni bir örnek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="b76a2-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="b76a2-119">Python 'dan kaynak tahmin aracı çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="b76a2-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="b76a2-120">Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan Q# işlemle kullanın:</span><span class="sxs-lookup"><span data-stu-id="b76a2-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="b76a2-121">Kaynak tahmin aracı 'ı komut satırından çağırma</span><span class="sxs-lookup"><span data-stu-id="b76a2-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="b76a2-122">Q#Komut satırından bir program çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="b76a2-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="b76a2-123">Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="b76a2-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="b76a2-124">Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma</span><span class="sxs-lookup"><span data-stu-id="b76a2-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="b76a2-125">Q#İşlemi çalıştırmak için I Magic komutunu [% Tahmini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın Q# .</span><span class="sxs-lookup"><span data-stu-id="b76a2-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="b76a2-126">Tahmini verileri program aracılığıyla alma</span><span class="sxs-lookup"><span data-stu-id="b76a2-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="b76a2-127">TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` .</span><span class="sxs-lookup"><span data-stu-id="b76a2-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="b76a2-128">`Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="b76a2-129">Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir işlem tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir Q# :</span><span class="sxs-lookup"><span data-stu-id="b76a2-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="b76a2-130">Bildirilen ölçümler</span><span class="sxs-lookup"><span data-stu-id="b76a2-130">Metrics Reported</span></span>

<span data-ttu-id="b76a2-131">Tahmin aracı kaynakları aşağıdaki ölçümleri izler:</span><span class="sxs-lookup"><span data-stu-id="b76a2-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="b76a2-132">Metric</span><span class="sxs-lookup"><span data-stu-id="b76a2-132">Metric</span></span>|<span data-ttu-id="b76a2-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b76a2-133">Description</span></span>|
|----|----|
|<span data-ttu-id="b76a2-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="b76a2-134">__CNOT__</span></span>    |<span data-ttu-id="b76a2-135">İşlemlerin çalıştırma sayısı `CNOT` (denetlenen Pauli X işlemleri olarak da bilinir).</span><span class="sxs-lookup"><span data-stu-id="b76a2-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="b76a2-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="b76a2-136">__QubitClifford__</span></span> |<span data-ttu-id="b76a2-137">Herhangi bir tek qubit Clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="b76a2-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="b76a2-138">__Measure__</span></span>    |<span data-ttu-id="b76a2-139">Ölçümlerin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="b76a2-140">__R__</span><span class="sxs-lookup"><span data-stu-id="b76a2-140">__R__</span></span>    |<span data-ttu-id="b76a2-141">Tüm tek qubit döndürmeler, hariç tutulan `T` , clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="b76a2-142">__T__</span><span class="sxs-lookup"><span data-stu-id="b76a2-142">__T__</span></span>    |<span data-ttu-id="b76a2-143">İşlemler `T` `T` , T_x = H. T. H ve T_y = HY. t. HY dahil olmak üzere işlemlerin ve bunların Birleşik kapılarının çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="b76a2-144">__Derinliğini__</span><span class="sxs-lookup"><span data-stu-id="b76a2-144">__Depth__</span></span>|<span data-ttu-id="b76a2-145">İşlem tarafından çalıştırılan hisse devdevlik derinliği Q# ( [aşağıya](#depth-width-and-qubitcount)bakın).</span><span class="sxs-lookup"><span data-stu-id="b76a2-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="b76a2-146">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="b76a2-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="b76a2-147">Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="b76a2-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="b76a2-148">__Genişlik__</span><span class="sxs-lookup"><span data-stu-id="b76a2-148">__Width__</span></span>|<span data-ttu-id="b76a2-149">İşlem tarafından çalıştırılan hisse devresi genişliği Q# ( [aşağıya](#depth-width-and-qubitcount)bakın).</span><span class="sxs-lookup"><span data-stu-id="b76a2-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="b76a2-150">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="b76a2-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="b76a2-151">Daha fazla ayrıntı için bkz. [Genişlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span><span class="sxs-lookup"><span data-stu-id="b76a2-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="b76a2-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="b76a2-152">__QubitCount__</span></span>    |<span data-ttu-id="b76a2-153">İşlemin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır Q# .</span><span class="sxs-lookup"><span data-stu-id="b76a2-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="b76a2-154">Bu ölçüm, __derinlemesine__ uyumlu olmayabilir (aşağıya bakın).</span><span class="sxs-lookup"><span data-stu-id="b76a2-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="b76a2-155">__Borrodilimlerin genişliği__</span><span class="sxs-lookup"><span data-stu-id="b76a2-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="b76a2-156">İşlem içinde ödünç alınan en fazla qubits sayısı Q# .</span><span class="sxs-lookup"><span data-stu-id="b76a2-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="b76a2-157">Derinlik, genişlik ve QubitCount</span><span class="sxs-lookup"><span data-stu-id="b76a2-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="b76a2-158">Bildirilen derinlik ve genişlik tahminleri birbirleriyle uyumludur.</span><span class="sxs-lookup"><span data-stu-id="b76a2-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="b76a2-159">(Daha önce iki sayı ulaşılabilir vardı, ancak derinlik ve genişlik için farklı devreler gerekli olacaktır.) Şu anda bu çiftteki ölçümler aynı anda aynı bağlantı hattı tarafından elde edilebilir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="b76a2-160">Aşağıdaki ölçümler raporlanır:</span><span class="sxs-lookup"><span data-stu-id="b76a2-160">The following metrics are reported:</span></span>

<span data-ttu-id="b76a2-161">__Derinlik:__ Kök işlem için, yapılandırılan ağ geçidi süreleri varsayarak yürütülmesi gereken süre.</span><span class="sxs-lookup"><span data-stu-id="b76a2-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="b76a2-162">İşlemin başındaki ve sonundaki en son qubit kullanılabilirlik süresi arasında veya sonraki işlem zamanı farkı olarak çağrılan işlemler için.</span><span class="sxs-lookup"><span data-stu-id="b76a2-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="b76a2-163">__Genişlik:__ Kök işlemi için-gerçekten yürütmek için kullanılan qubits sayısı (ve çağrı yaptığı işlem).</span><span class="sxs-lookup"><span data-stu-id="b76a2-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="b76a2-164">Ya da sonraki işlemleri çağıran işlemler için-işlemin başlangıcında zaten kullanılan qubits 'e ek olarak kaç tane daha fazla bilgi kullanılmıştır.</span><span class="sxs-lookup"><span data-stu-id="b76a2-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="b76a2-165">Lütfen bu sayı ile yeniden kullanılan qubits 'in bu numaraya katkıda bulunduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b76a2-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="b76a2-166">Yani, işlem A 'dan önce birkaç qubit yayımlandıysa ve bu işlem tarafından (ve ' dan çağırılan işlemler) talep edilen tüm qubit, daha önce sürüm qubit yeniden kullanılmasıyla karşılandıysa, A işleminin genişliği 0 olarak bildirilir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="b76a2-167">Başarıyla ödünç alınan qubits, genişliğe katkıda bulunmuyor.</span><span class="sxs-lookup"><span data-stu-id="b76a2-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="b76a2-168">__Qubitcount:__ Kök işlemi için-bu işlemi (ve öğesinden çağrılan işlemleri) yürütmek için yeterli olacak qubit sayısı alt sınırı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="b76a2-169">Veya sonraki işlemleri çağıran işlemler için-bu işlemi ayrı olarak yürütmek için yeterli olacak qubit sayısı alt sınırı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="b76a2-170">Bu sayı giriş qubitleri içermez.</span><span class="sxs-lookup"><span data-stu-id="b76a2-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="b76a2-171">Ödünç alınan qubit içerir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="b76a2-172">İki işlem modu desteklenir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-172">Two modes of operation are supported.</span></span> <span data-ttu-id="b76a2-173">QCTraceSimulatorConfiguration. OptimizeDepth ayarlanarak mod seçilidir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="b76a2-174">__Optimizedepth = false:__ Bu varsayılan moddur.</span><span class="sxs-lookup"><span data-stu-id="b76a2-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="b76a2-175">QubitManager 'ın qubit 'i yeniden kullanması önerilir ve yenilerini ayırmadan önce yayınlanmış qubits 'i yeniden kullanacaktır.</span><span class="sxs-lookup"><span data-stu-id="b76a2-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="b76a2-176">Kök işlemi __genişliği__ için en az Genişlik (alt sınır) olur.</span><span class="sxs-lookup"><span data-stu-id="b76a2-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="b76a2-177">Uyumluluk __derinliğine__ ulaşıldığı bildirilir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="b76a2-178">__Qubitcount__ , hiçbir ödünç alma kabul edildiğinde kök işlemin __genişliğiyle__ aynı olacak.</span><span class="sxs-lookup"><span data-stu-id="b76a2-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="b76a2-179">__Optimizedepth = doğru:__ QubitManager 'ın qubit yeniden kullanımı önerilmez ve yürütme sırasında ve sonrasında qubit yeniden kullanımı için buluşsal-tabanlı iyileştirme gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="b76a2-180">Kök işlemi __derinliği__ için en düşük Derinlik (alt sınır) olur.</span><span class="sxs-lookup"><span data-stu-id="b76a2-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="b76a2-181">Bu derinlik için uyumlu __Genişlik__ raporlanır (her ikisi de aynı anda elde edilebilir).</span><span class="sxs-lookup"><span data-stu-id="b76a2-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="b76a2-182">Genişliği iyileştirmek için, programda daha sonra karşılaşılan kapılar programda daha önce kullanılmadan önce zamanlanabilir, ancak qubits, derinlik en az kalacak şekilde yeniden kullanılmak üzere zamanlandı.</span><span class="sxs-lookup"><span data-stu-id="b76a2-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="b76a2-183">Qubits, zaman değerlerine göre yeniden kullanıldığı için, geçit sürelerinin tamsayı değerler olacak şekilde yapılandırılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="b76a2-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="b76a2-184">__Genişliğin__ en iyi şekilde garanti edilmez.</span><span class="sxs-lookup"><span data-stu-id="b76a2-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="b76a2-185">Daha fazla bilgi için, [izleme sırasında teknik Inceleme genişliği ve derinliğinde](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="b76a2-186">Ölçüm sonuçlarının olasılığını sağlama</span><span class="sxs-lookup"><span data-stu-id="b76a2-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="b76a2-187"><xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> <xref:Microsoft.Quantum.Diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="b76a2-188">Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="b76a2-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="b76a2-189">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="b76a2-189">See also</span></span>

- [<span data-ttu-id="b76a2-190">Hisse izi izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="b76a2-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="b76a2-191">Kuantum Toffoli simülatörü</span><span class="sxs-lookup"><span data-stu-id="b76a2-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="b76a2-192">Kuantum tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="b76a2-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
