---
title: Hisse kaynakları tahmin aracı-hisse geliştirme seti
description: 'Bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden Microsoft QDK kaynakları Estimator hakkında bilgi edinin :::no-loc(Q#)::: .'
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e1ec01d85a141b9c8a7a5ba5589663a0773520e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691865"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="dedc0-103">Hisse geliştirme seti (QDK) kaynakları tahmin aracı</span><span class="sxs-lookup"><span data-stu-id="dedc0-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="dedc0-104">Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı :::no-loc(Q#)::: bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="dedc0-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a :::no-loc(Q#)::: operation on a quantum computer.</span></span> <span data-ttu-id="dedc0-105">Bu işlemi, hisse bir bilgisayarın durumunun benzetimini yapmadan hisse, işlem işlemini çalıştırarak gerçekleştirir; Bu nedenle, :::no-loc(Q#)::: kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan işlemler için kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="dedc0-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for :::no-loc(Q#)::: operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="dedc0-106">Kaynaklar, hata ayıklama programlarında yardımcı olacak daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="dedc0-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug :::no-loc(Q#)::: programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="dedc0-107">Kaynak tahmin aracı 'ı çağırma ve çalıştırma</span><span class="sxs-lookup"><span data-stu-id="dedc0-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="dedc0-108">Herhangi bir işlemi çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="dedc0-108">You can use the resources estimator to run any :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="dedc0-109">Daha fazla bilgi için bkz. [ :::no-loc(Q#)::: Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).</span><span class="sxs-lookup"><span data-stu-id="dedc0-109">For additional details, see [Ways to run a :::no-loc(Q#)::: program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="dedc0-110">C 'den kaynak tahmin aracı çağrılıyor #</span><span class="sxs-lookup"><span data-stu-id="dedc0-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="dedc0-111">Diğer hedef makinelerde olduğu gibi, önce `ResourceEstimator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dedc0-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="dedc0-112">`QuantumSimulator` sınıfının aksine, `ResourceEstimator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="dedc0-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="dedc0-113">Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` sekmeyle ayrılmış değerler (TSV) içeren bir tablo üreten yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="dedc0-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="dedc0-114">Tabloyu bir dosyaya kaydedebilir veya analiz için konsolda görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dedc0-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="dedc0-115">Aşağıda, önceki programın örnek bir çıktısı verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="dedc0-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="dedc0-116">`ResourcesEstimator`Örnek, her çalıştırmada hesaplamalarını sıfırlamaz.</span><span class="sxs-lookup"><span data-stu-id="dedc0-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="dedc0-117">Başka bir işlem çalıştırmak için aynı örneği kullanırsanız, yeni sonuçları mevcut sonuçlarla toplar.</span><span class="sxs-lookup"><span data-stu-id="dedc0-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="dedc0-118">Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her çalıştırma için yeni bir örnek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="dedc0-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="dedc0-119">Python 'dan kaynak tahmin aracı çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="dedc0-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="dedc0-120">Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan :::no-loc(Q#)::: işlemle kullanın:</span><span class="sxs-lookup"><span data-stu-id="dedc0-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported :::no-loc(Q#)::: operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="dedc0-121">Kaynak tahmin aracı 'ı komut satırından çağırma</span><span class="sxs-lookup"><span data-stu-id="dedc0-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="dedc0-122">:::no-loc(Q#):::Komut satırından bir program çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` .</span><span class="sxs-lookup"><span data-stu-id="dedc0-122">When running a :::no-loc(Q#)::: program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="dedc0-123">Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır:</span><span class="sxs-lookup"><span data-stu-id="dedc0-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="dedc0-124">Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma</span><span class="sxs-lookup"><span data-stu-id="dedc0-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="dedc0-125">:::no-loc(Q#):::İşlemi çalıştırmak için I Magic komutunu [% Tahmini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="dedc0-125">Use the I:::no-loc(Q#)::: magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the :::no-loc(Q#)::: operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="dedc0-126">Tahmini verileri program aracılığıyla alma</span><span class="sxs-lookup"><span data-stu-id="dedc0-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="dedc0-127">TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` .</span><span class="sxs-lookup"><span data-stu-id="dedc0-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="dedc0-128">`Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="dedc0-129">Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir işlem tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir :::no-loc(Q#)::: :</span><span class="sxs-lookup"><span data-stu-id="dedc0-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a :::no-loc(Q#)::: operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="dedc0-130">Bildirilen ölçümler</span><span class="sxs-lookup"><span data-stu-id="dedc0-130">Metrics Reported</span></span>

<span data-ttu-id="dedc0-131">Tahmin aracı kaynakları aşağıdaki ölçümleri izler:</span><span class="sxs-lookup"><span data-stu-id="dedc0-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="dedc0-132">Ölçüm</span><span class="sxs-lookup"><span data-stu-id="dedc0-132">Metric</span></span>|<span data-ttu-id="dedc0-133">Açıklama</span><span class="sxs-lookup"><span data-stu-id="dedc0-133">Description</span></span>|
|----|----|
|<span data-ttu-id="dedc0-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="dedc0-134">__CNOT__</span></span>    |<span data-ttu-id="dedc0-135">İşlemlerin çalıştırma sayısı `CNOT` (denetlenen Pauli X işlemleri olarak da bilinir).</span><span class="sxs-lookup"><span data-stu-id="dedc0-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="dedc0-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="dedc0-136">__QubitClifford__</span></span> |<span data-ttu-id="dedc0-137">Herhangi bir tek qubit Clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="dedc0-138">__Measure__</span><span class="sxs-lookup"><span data-stu-id="dedc0-138">__Measure__</span></span>    |<span data-ttu-id="dedc0-139">Ölçümlerin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="dedc0-140">__R__</span><span class="sxs-lookup"><span data-stu-id="dedc0-140">__R__</span></span>    |<span data-ttu-id="dedc0-141">Tüm tek qubit döndürmeler, hariç tutulan `T` , clienfford ve Pauli işlemlerinin çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="dedc0-142">__T__</span><span class="sxs-lookup"><span data-stu-id="dedc0-142">__T__</span></span>    |<span data-ttu-id="dedc0-143">İşlemler `T` `T` , T_x = H. T. H ve T_y = HY. t. HY dahil olmak üzere işlemlerin ve bunların Birleşik kapılarının çalıştırma sayısı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="dedc0-144">__Derinliğini__</span><span class="sxs-lookup"><span data-stu-id="dedc0-144">__Depth__</span></span>|<span data-ttu-id="dedc0-145">İşlem tarafından çalıştırılan hisse devdevlik derinliği :::no-loc(Q#)::: ( [aşağıya](#depth-width-and-qubitcount)bakın).</span><span class="sxs-lookup"><span data-stu-id="dedc0-145">Depth of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="dedc0-146">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="dedc0-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="dedc0-147">Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="dedc0-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="dedc0-148">__Genişlik__</span><span class="sxs-lookup"><span data-stu-id="dedc0-148">__Width__</span></span>|<span data-ttu-id="dedc0-149">İşlem tarafından çalıştırılan hisse devresi genişliği :::no-loc(Q#)::: ( [aşağıya](#depth-width-and-qubitcount)bakın).</span><span class="sxs-lookup"><span data-stu-id="dedc0-149">Width of the quantum circuit run by the :::no-loc(Q#)::: operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="dedc0-150">Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` .</span><span class="sxs-lookup"><span data-stu-id="dedc0-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="dedc0-151">Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span><span class="sxs-lookup"><span data-stu-id="dedc0-151">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="dedc0-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="dedc0-152">__QubitCount__</span></span>    |<span data-ttu-id="dedc0-153">İşlemin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="dedc0-153">The lower bound for the maximum number of qubits allocated during the run of the :::no-loc(Q#)::: operation.</span></span> <span data-ttu-id="dedc0-154">Bu ölçüm, __derinlemesine__ uyumlu olmayabilir (aşağıya bakın).</span><span class="sxs-lookup"><span data-stu-id="dedc0-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="dedc0-155">__Borrodilimlerin genişliği__</span><span class="sxs-lookup"><span data-stu-id="dedc0-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="dedc0-156">İşlem içinde ödünç alınan en fazla qubits sayısı :::no-loc(Q#)::: .</span><span class="sxs-lookup"><span data-stu-id="dedc0-156">The maximum number of qubits borrowed inside the :::no-loc(Q#)::: operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="dedc0-157">Derinlik, genişlik ve QubitCount</span><span class="sxs-lookup"><span data-stu-id="dedc0-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="dedc0-158">Bildirilen derinlik ve genişlik tahminleri birbirleriyle uyumludur.</span><span class="sxs-lookup"><span data-stu-id="dedc0-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="dedc0-159">(Daha önce iki sayı ulaşılabilir vardı, ancak derinlik ve genişlik için farklı devreler gerekli olacaktır.) Şu anda bu çiftteki ölçümler aynı anda aynı bağlantı hattı tarafından elde edilebilir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="dedc0-160">Aşağıdaki ölçümler raporlanır:</span><span class="sxs-lookup"><span data-stu-id="dedc0-160">The following metrics are reported:</span></span>

<span data-ttu-id="dedc0-161">__Derinlik:__ Kök işlemi için-belirli bir kapı süresi varsayarak yürütülmesi gereken süre.</span><span class="sxs-lookup"><span data-stu-id="dedc0-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="dedc0-162">Ya da işlem sırasında en son qubit kullanılabilirlik süresi arasında gerçekleştirilen işlemler veya sonraki işlemler için zaman farkı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="dedc0-163">__Genişlik:__ Kök işlemi için-gerçekten yürütmek için kullanılan qubits sayısı (ve çağrı yaptığı işlem).</span><span class="sxs-lookup"><span data-stu-id="dedc0-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="dedc0-164">Ya da sonraki işlemleri çağıran işlemler için-işlemin başlangıcında zaten kullanılan qubits 'e ek olarak kaç tane daha fazla bilgi kullanılmıştır.</span><span class="sxs-lookup"><span data-stu-id="dedc0-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="dedc0-165">Lütfen bu sayı ile yeniden kullanılan qubits 'in bu numaraya katkıda bulunduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="dedc0-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="dedc0-166">Yani, işlem A 'dan önce birkaç qubit yayımlandıysa ve bu işlem tarafından (ve ' dan çağırılan işlemler) talep edilen tüm qubit, daha önce sürüm qubit yeniden kullanılmasıyla karşılandıysa, A işleminin genişliği 0 olarak bildirilir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="dedc0-167">Başarıyla ödünç alınan qubits, genişliğe katkıda bulunmuyor.</span><span class="sxs-lookup"><span data-stu-id="dedc0-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="dedc0-168">__Qubitcount:__ Kök işlemi için-bu işlemi (ve öğesinden çağrılan işlemleri) yürütmek için yeterli olacak qubit sayısı alt sınırı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="dedc0-169">Veya sonraki işlemleri çağıran işlemler için-bu işlemi ayrı olarak yürütmek için yeterli olacak qubit sayısı alt sınırı.</span><span class="sxs-lookup"><span data-stu-id="dedc0-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="dedc0-170">Bu sayı giriş qubitleri içermez.</span><span class="sxs-lookup"><span data-stu-id="dedc0-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="dedc0-171">Ödünç alınan qubit içerir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="dedc0-172">İki işlem modu desteklenir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-172">Two modes of operation are supported.</span></span> <span data-ttu-id="dedc0-173">QCTraceSimulatorConfiguration. OptimizeDepth ayarlanarak mod seçilidir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="dedc0-174">__Optimizedepth = doğru:__ QubitManager 'ın qubit yeniden kullanımı önerilmez ve her sorulduğunda her istendiğinde yeni qubit 'i ayırır.</span><span class="sxs-lookup"><span data-stu-id="dedc0-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="dedc0-175">Kök işlemi __derinliği__ için en düşük Derinlik (alt sınır) olur.</span><span class="sxs-lookup"><span data-stu-id="dedc0-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="dedc0-176">Bu derinlik için uyumlu __Genişlik__ raporlanır (her ikisi de aynı anda elde edilebilir).</span><span class="sxs-lookup"><span data-stu-id="dedc0-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="dedc0-177">Bu genişliğin büyük olasılıkla bu derinliğin en iyi şekilde verilmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="dedc0-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="dedc0-178">__Qubitcount__ , yeniden kullanım varsaydığı için kök işlem genişliğinden daha düşük olabilir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="dedc0-179">__Optimizedepth = false:__ QubitManager 'ın qubit 'i yeniden kullanması önerilir ve yenilerini ayırmadan önce yayınlanmış qubits 'i yeniden kullanacaktır.</span><span class="sxs-lookup"><span data-stu-id="dedc0-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="dedc0-180">Kök işlemi __genişliği__ için en az Genişlik (alt sınır) olur.</span><span class="sxs-lookup"><span data-stu-id="dedc0-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="dedc0-181">Uyumluluk __derinliğine__ ulaşıldığı bildirilir.</span><span class="sxs-lookup"><span data-stu-id="dedc0-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="dedc0-182">__Qubitcount__ , hiçbir ödünç alma kabul edildiğinde kök işlemin __genişliğiyle__ aynı olacak.</span><span class="sxs-lookup"><span data-stu-id="dedc0-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="dedc0-183">Ölçüm sonuçlarının olasılığını sağlama</span><span class="sxs-lookup"><span data-stu-id="dedc0-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="dedc0-184"><xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> <xref:Microsoft.Quantum.Diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="dedc0-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="dedc0-185">Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="dedc0-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="dedc0-186">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="dedc0-186">See also</span></span>

- [<span data-ttu-id="dedc0-187">Hisse izi izleme simülatörü</span><span class="sxs-lookup"><span data-stu-id="dedc0-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="dedc0-188">Kuantum Toffoli simülatörü</span><span class="sxs-lookup"><span data-stu-id="dedc0-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="dedc0-189">Kuantum tam durum simülatörü</span><span class="sxs-lookup"><span data-stu-id="dedc0-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
