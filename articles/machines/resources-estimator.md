---
title: Hisse geliştirme seti kaynakları Estimator
description: "Bir hisse bilgisayar üzerinde Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden kaynakların Estimator 'ı hakkında bilgi edinin."
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630126"
---
# <a name="the-resources-estimator-target-machine"></a>Kaynaklar Estimator hedef makine

Adından da anlaşılacağı gibi, `ResourcesEstimator` bir hisse bilgisayarındaki Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder.
Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, kodun klasik bölümü makul bir süre içinde çalıştırılabilecekse binlerce qubit kullanan Q # işlemlerine yönelik kaynakları tahmin edebilir.

## <a name="usage"></a>Kullanım

`ResourcesEstimator`Yalnızca başka bir hedef makine türüdür, bu nedenle herhangi bir Q # işlemini çalıştırmak için kullanılabilir. 

Diğer hedef makineler olarak, bir C# ana bilgisayar programında kullanmak için bir örnek oluşturun ve bunu işlem yönteminin ilk parametresi olarak geçirin `Run` :

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

Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` bir dosyaya kaydedilebilecek veya analiz edilmek üzere konsola yazılabilen sekmeyle ayrılmış değerler (TSV) içeren bir tablo oluşturmak için bir yöntem sağlar. Yukarıdaki programın çıktısı şuna benzemelidir:

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
> `ResourcesEstimator`Her çalıştırmada hesaplamalarını sıfırlamaz, başka bir işlem yürütmek için aynı örnek kullanılırsa, mevcut sonuçların üzerine toplama sayılarını saklar.
> Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her yürütme için yeni bir örnek oluşturun.


## <a name="programmatically-retrieving-the-estimated-data"></a>Tahmini verileri program aracılığıyla alma

TSV tablosuna ek olarak, tahmini kaynaklar, özelliği aracılığıyla program aracılığıyla alınabilir `ResourcesEstimator` `Data` . `Data``System.DataTable`iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarıyla dizine alınır.

Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir Q # işlemi tarafından kullanılan toplam ve kapı sayısını alma ve yazdırmanın nasıl yapılacağını gösterir:

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

Aşağıda tarafından tahmin edilen ölçümlerin listesi verilmiştir `ResourcesEstimator` :

* __Cnot__: yürütülen cnot (denetlenen Pauli X kapısı olarak da bilinir) kapıları sayısı.
* __Qubitclifford__: herhangi bir tek qubit Clienfford ve Pauli Gates 'in sayısı yürütüldü.
* __Measure__: yürütülen ölçüm sayısı.
* __R__: T, Clienfford ve Pauli Gates hariç çalıştırılan tek qubit döndürmeler sayısı.
* __T__: t kapısı, T_x = H. T. H ve T_y = HY. t. HY de dahil olmak üzere, t kapıları ve bunların Birleşik kapılarının sayısı.
* __Derinlik__: Q # işlemi tarafından yürütülen hisse devresi derinliği. Varsayılan olarak, derinlemesine yalnızca T kapıları sayılır, Ayrıntılar için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) .
* __Width__: Q # işleminin yürütülmesi sırasında ayrılan en fazla qubit sayısı.
* __Borrodilimlerin genişliği__: Q # işlemi içinde ödünç alınan en fazla qubits sayısı.


## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm Sonuçlarının Olasılığını Sağlama

<xref:microsoft.quantum.intrinsic.assertprob>ad alanından, <xref:microsoft.quantum.intrinsic> Q # programının yürütülmesini sağlamaya yardımcı olmak üzere bir ölçünün beklenen olasılığı hakkında bilgi sağlamak için kullanılabilir. Aşağıdaki örnekte bu gösterilmektedir:

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

Bu, `ResourcesEstimator` `AssertProb` `PauliZ` `source` `q` ölçmeye çalıştığı ve olasılık 0,5 ile ilgili bir sonucu verilmelidir `Zero` . `M`Daha sonra çalıştırıldığında, sonuç olasılıkların kayıtlı değerlerini bulur ve `M` 0,5 ile geri dönecektir `Zero` `One` .


## <a name="see-also"></a>Ayrıca bkz.

, `ResourcesEstimator` Daha zengin bir ölçüm kümesi sunan hisse bilgisayar [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur. Bu, tam çağrı grafiğinde ölçümleri rapor etme ve Q # programlarında hata bulmaya yardımcı olması için [ayrı girişler denetleyicisi](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) gibi özellikler sağlar. Daha fazla bilgi için lütfen [izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro) belgelerine bakın.

