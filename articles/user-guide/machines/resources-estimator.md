---
title: Hisse kaynakları tahmin aracı-hisse geliştirme seti
description: Bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eden Microsoft QDK kaynakları Estimator hakkında bilgi edinin Q# .
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6138c098a4efe2797c7d7360573ddcb9cb70a6c1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835936"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Hisse geliştirme seti (QDK) kaynakları tahmin aracı

Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı Q# bir hisse bilgisayar üzerinde bir işlemin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder. Bu işlemi, hisse bir bilgisayarın durumunun benzetimini yapmadan hisse, işlem işlemini çalıştırarak gerçekleştirir; Bu nedenle, Q# kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan işlemler için kaynakları tahmin eder.

Kaynaklar, hata ayıklama programlarında yardımcı olacak daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur Q# .

## <a name="invoking-and-running-the-resources-estimator"></a>Kaynak tahmin aracı 'ı çağırma ve çalıştırma

Herhangi bir işlemi çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz Q# . Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>C 'den kaynak tahmin aracı çağrılıyor # 

Diğer hedef makinelerde olduğu gibi, önce `ResourceEstimator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.

`QuantumSimulator` sınıfının aksine, `ResourceEstimator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.

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

Örnekte gösterildiği gibi, `ResourcesEstimator` `ToTSV()` sekmeyle ayrılmış değerler (TSV) içeren bir tablo üreten yöntemi sağlar. Tabloyu bir dosyaya kaydedebilir veya analiz için konsolda görüntüleyebilirsiniz. Aşağıda, önceki programın örnek bir çıktısı verilmiştir:

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
> `ResourcesEstimator`Örnek, her çalıştırmada hesaplamalarını sıfırlamaz. Başka bir işlem çalıştırmak için aynı örneği kullanırsanız, yeni sonuçları mevcut sonuçlarla toplar. Çalıştırmalar arasında hesaplamaları sıfırlamanız gerekiyorsa, her çalıştırma için yeni bir örnek oluşturun.

### <a name="invoking-the-resources-estimator-from-python"></a>Python 'dan kaynak tahmin aracı çağrılıyor

Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan Q# işlemle kullanın:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Kaynak tahmin aracı 'ı komut satırından çağırma

Q#Komut satırından bir program çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` . Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma

Q#İşlemi çalıştırmak için I Magic komutunu [% Tahmini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın Q# .

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Tahmini verileri program aracılığıyla alma

TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` . `Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.

Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir işlem tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir Q# :

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

Tahmin aracı kaynakları aşağıdaki ölçümleri izler:

|Ölçüm|Açıklama|
|----|----|
|__CNOT__    |İşlemlerin çalıştırma sayısı `CNOT` (denetlenen Pauli X işlemleri olarak da bilinir).|
|__QubitClifford__ |Herhangi bir tek qubit Clienfford ve Pauli işlemlerinin çalıştırma sayısı.|
|__Measure (Ölçü)__     |Ölçümlerin çalıştırma sayısı.  |
|__R__    |Tüm tek qubit döndürmeler, hariç tutulan `T` , clienfford ve Pauli işlemlerinin çalıştırma sayısı.  |
|__T__    |İşlemler `T` `T` , T_x = H. T. H ve T_y = HY. t. HY dahil olmak üzere işlemlerin ve bunların Birleşik kapılarının çalıştırma sayısı.  |
|__Derinliğini__|İşlem tarafından çalıştırılan hisse devdevlik derinliğine yönelik alt sınır Q# . Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` . Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Genişlik__    |İşlemin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır Q# . Aynı anda hem __derinlik__ hem de __Genişlik__ alt sınırlarına ulaşmak mümkün olmayabilir.  |
|__Borrodilimlerin genişliği__    |İşlem içinde ödünç alınan en fazla qubits sayısı Q# .  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm sonuçlarının olasılığını sağlama

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz. Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Ayrıca bkz.

- [Hisse izi izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Kuantum Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator)
- [Kuantum tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) 