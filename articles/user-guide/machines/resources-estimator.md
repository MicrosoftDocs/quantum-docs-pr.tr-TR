---
title: Hisse geliştirme seti kaynakları Estimator
description: "Bir hisse bilgisayar üzerinde Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden kaynakların Estimator 'ı hakkında bilgi edinin."
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275551"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="c6e7e-103">Kaynaklar Estimator hedef makine</span><span class="sxs-lookup"><span data-stu-id="c6e7e-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="c6e7e-104">Adından da anlaşılacağı gibi, `ResourcesEstimator` bir hisse bilgisayarındaki Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="c6e7e-105">Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, kodun klasik bölümü makul bir süre içinde çalıştırılabilecekse binlerce qubit kullanan Q # işlemlerine yönelik kaynakları tahmin edebilir.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="c6e7e-106">Kullanım</span><span class="sxs-lookup"><span data-stu-id="c6e7e-106">Usage</span></span>

<span data-ttu-id="c6e7e-107">`ResourcesEstimator`Yalnızca başka bir hedef makine türüdür, bu nedenle herhangi bir Q # işlemini çalıştırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="c6e7e-108">Diğer hedef makineler olarak, bir C# ana bilgisayar programında kullanmak için bir örnek oluşturun ve bunu işlem yönteminin ilk parametresi olarak geçirin `Run` :</span><span class="sxs-lookup"><span data-stu-id="c6e7e-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

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

<span data-ttu-id="c6e7e-109">Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` bir dosyaya kaydedilebilecek veya analiz edilmek üzere konsola yazılabilen sekmeyle ayrılmış değerler (TSV) içeren bir tablo oluşturmak için bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="c6e7e-110">Yukarıdaki programın çıktısı şuna benzemelidir:</span><span class="sxs-lookup"><span data-stu-id="c6e7e-110">The output of the above program should look something like this:</span></span>

```Output
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
> <span data-ttu-id="c6e7e-111">`ResourcesEstimator`Her çalıştırmada hesaplamalarını sıfırlamaz, başka bir işlem yürütmek için aynı örnek kullanılırsa, mevcut sonuçların üzerine toplama sayılarını saklar.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="c6e7e-112">Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her yürütme için yeni bir örnek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="c6e7e-113">Tahmini verileri program aracılığıyla alma</span><span class="sxs-lookup"><span data-stu-id="c6e7e-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="c6e7e-114">TSV tablosuna ek olarak, tahmini kaynaklar, özelliği aracılığıyla program aracılığıyla alınabilir `ResourcesEstimator` `Data` .</span><span class="sxs-lookup"><span data-stu-id="c6e7e-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="c6e7e-115">`Data``System.DataTable`iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarıyla dizine alınır.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="c6e7e-116">Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir Q # işlemi tarafından kullanılan toplam ve kapı sayısını alma ve yazdırmanın nasıl yapılacağını gösterir:</span><span class="sxs-lookup"><span data-stu-id="c6e7e-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="c6e7e-117">Bildirilen ölçümler</span><span class="sxs-lookup"><span data-stu-id="c6e7e-117">Metrics Reported</span></span>

<span data-ttu-id="c6e7e-118">Aşağıda tarafından tahmin edilen ölçümlerin listesi verilmiştir `ResourcesEstimator` :</span><span class="sxs-lookup"><span data-stu-id="c6e7e-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="c6e7e-119">__Cnot__: yürütülen cnot (denetlenen Pauli X kapısı olarak da bilinir) kapıları sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="c6e7e-120">__Qubitclifford__: herhangi bir tek qubit Clienfford ve Pauli Gates 'in sayısı yürütüldü.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="c6e7e-121">__Measure__: yürütülen ölçüm sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="c6e7e-122">__R__: T, Clienfford ve Pauli Gates hariç çalıştırılan tek qubit döndürmeler sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="c6e7e-123">__T__: t kapısı, T_x = H. T. H ve T_y = HY. t. HY de dahil olmak üzere, t kapıları ve bunların Birleşik kapılarının sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="c6e7e-124">__Derinlik__: Q # işlemi tarafından yürütülen hisse devresi derinliği.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="c6e7e-125">Varsayılan olarak, derinlemesine yalnızca T kapıları sayılır, Ayrıntılar için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .</span><span class="sxs-lookup"><span data-stu-id="c6e7e-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="c6e7e-126">__Width__: Q # işleminin yürütülmesi sırasında ayrılan en fazla qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="c6e7e-127">__Borrodilimlerin genişliği__: Q # işlemi içinde ödünç alınan en fazla qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="c6e7e-128">Ölçüm Sonuçlarının Olasılığını Sağlama</span><span class="sxs-lookup"><span data-stu-id="c6e7e-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="c6e7e-129"><xref:microsoft.quantum.intrinsic.assertprob>ad alanından, <xref:microsoft.quantum.intrinsic> Q # programının yürütülmesini sağlamaya yardımcı olmak üzere bir ölçünün beklenen olasılığı hakkında bilgi sağlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="c6e7e-130">Aşağıdaki örnekte bu gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="c6e7e-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="c6e7e-131">Bu, `ResourcesEstimator` `AssertProb` `PauliZ` `source` `q` ölçmeye çalıştığı ve olasılık 0,5 ile ilgili bir sonucu verilmelidir `Zero` .</span><span class="sxs-lookup"><span data-stu-id="c6e7e-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="c6e7e-132">`M`Daha sonra çalıştırıldığında, sonuç olasılıkların kayıtlı değerlerini bulur ve `M` 0,5 ile geri dönecektir `Zero` `One` .</span><span class="sxs-lookup"><span data-stu-id="c6e7e-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="c6e7e-133">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-133">See also</span></span>

<span data-ttu-id="c6e7e-134">, `ResourcesEstimator` Daha zengin bir ölçüm kümesi sunan hisse bilgisayar [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur. Bu, tam çağrı grafiğinde ölçümleri rapor etme ve Q # programlarında hata bulmaya yardımcı olması için [ayrı girişler denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) gibi özellikler sağlar.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="c6e7e-135">Daha fazla bilgi için lütfen [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="c6e7e-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

