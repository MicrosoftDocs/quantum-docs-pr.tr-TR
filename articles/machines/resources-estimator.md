---
title: Hisse geliştirme seti kaynakları tahmini | Microsoft Docs
description: Microsoft 'un hisse geliştirme seti kaynakları tahmin aracı 'a genel bakış
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: 591e306b3001934bd81342a533e3f6ca25129781
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184993"
---
# <a name="the-resourcesestimator-target-machine"></a>ResourcesEstimator hedef makinesi

Adından da anlaşılacağı gibi `ResourcesEstimator`, bir hisse bilgisayar üzerinde Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.
Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, binlerce qubit kullanan Q # işlemlerine yönelik kaynakları tahmin edebilir.

## <a name="usage"></a>Kullanım

`ResourcesEstimator` yalnızca başka bir hedef makine türüdür, bu nedenle herhangi bir Q # işlemini çalıştırmak için kullanılabilir. 

Diğer hedef makineler olarak, bir C# konak programda kullanmak için bir örnek oluşturun ve bunu işlemin `Run` yönteminin ilk parametresi olarak geçirin:

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

Örnekte gösterildiği gibi, `ResourcesEstimator`, bir dosyaya kaydedilebilecek veya analiz edilmek üzere konsola yazıtabilerek sekmeyle ayrılmış değerler (TSV) içeren bir tablo oluşturmak için bir `ToTSV()` yöntemi sağlar. Yukarıdaki programın çıktısı şuna benzemelidir:

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
> `ResourcesEstimator`, her çalıştırmada hesaplamalarını sıfırlamaz ve aynı örnek başka bir işlem yürütmek için kullanılırsa, mevcut sonuçların üzerine toplama sayılarını saklar.
> Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her yürütme için yeni bir örnek oluşturun.


## <a name="programmatically-retrieving-the-estimated-data"></a>Tahmini verileri program aracılığıyla alma

TSV tablosuna ek olarak, tahmini kaynaklar `ResourcesEstimator``Data` özelliği aracılığıyla program aracılığıyla alınabilir. `Data`, ölçüm adlarıyla dizine alınmış `Metric` ve `Sum`olmak üzere iki sütunlu `System.DataTable` bir örnek sağlar.

Aşağıdaki kod, bir Q # işlemi tarafından kullanılan `QubitClifford`, `T` ve `CNOT` kapıların toplam sayısını nasıl alacağınızı ve yazdırakullanacağınızı gösterir:

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

## <a name="metrics-reported"></a>Bildirilen ölçümler

`ResourcesEstimator`tarafından tahmin edilen ölçümlerin listesi aşağıda verilmiştir:

* __Cnot__: yürütülen cnot (denetlenen Pauli X kapısı olarak da bilinir) kapıları sayısı.
* __Qubitclifford__: herhangi bir tek qubit Clienfford ve Pauli Gates 'in sayısı yürütüldü.
* __Measure__: yürütülen ölçüm sayısı.
* __R__: T, Clienfford ve Pauli Gates hariç çalıştırılan tek qubit döndürmeler sayısı.
* __T__: t kapısı ve T_x = H. t. H ve T_y = HY. T. HY dahil olmak üzere onların ve bunların Birleşik kapıları sayısı.
* __Derinlik__: Q # işlemi tarafından yürütülen hisse devresi derinliği. Varsayılan olarak, derinlemesine yalnızca T kapıları sayılır, Ayrıntılar için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: Q # işleminin yürütülmesi sırasında ayrılan en fazla qubit sayısı.
* __Borrodilimlerin genişliği__: Q # işlemi içinde ödünç alınan en fazla qubits sayısı.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm sonuçları olasılığını sağlama

<xref:microsoft.quantum.primitive> ad alanından <xref:microsoft.quantum.primitive.assertprob>, Q # programının yürütülmesini sağlamaya yardımcı olmak üzere bir ölçünün beklenen olasılığı hakkında bilgi sağlamak için kullanılabilir. Aşağıdaki örnek şunu göstermektedir:

```qsharp
operation Teleportation (source : Qubit, target : Qubit) : Unit {

    using (ancilla = Qubit()) {

        H(ancilla);
        CNOT(ancilla, target);

        CNOT(source, ancilla);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [ancilla], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(ancilla) == One) { X(target); X(ancilla); }
    }
}
```

`ResourcesEstimator` karşılaştığında `AssertProb` `PauliZ` ölçmeye `source` ve `ancilla`, olasılık 0,5 ile `Zero` sonucunu verilmelidir. Daha sonra `M` yürüttüğünde, sonuç olasılıkların kayıtlı değerlerini bulur ve `M` olasılık 0,5 ile `Zero` veya `One` döndürür.


## <a name="see-also"></a>Ayrıca bkz.

`ResourcesEstimator`, daha zengin bir ölçüm kümesi sunan hisse bilgisayar [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur. Bu, tam çağrı grafiğinde ölçümleri rapor etme özelliğini ve Q # programlarında hata bulmaya yardımcı olması için [ayrı girişler denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) gibi özellikleri sağlar. Daha fazla bilgi için lütfen [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) belgelerine bakın.

