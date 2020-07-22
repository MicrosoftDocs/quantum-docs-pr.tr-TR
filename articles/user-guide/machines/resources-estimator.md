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
# <a name="quantum-development-kit-qdk-resources-estimator"></a>Hisse geliştirme seti (QDK) kaynakları tahmin aracı

Adından da anlaşılacağı gibi, `ResourcesEstimator` sınıfı bir hisse bilgisayar üzerinde Q # işleminin belirli bir örneğini çalıştırmak için gereken kaynakları tahmin eder. Bu işlemi, bir hisse bilgisayarının durumunu gerçekten taklit etmeden hisse yürütme işlemini gerçekleştirerek gerçekleştirir; Bu nedenle, kodun klasik kısmının makul bir süre içinde çalışması şartıyla, binlerce qubit kullanan Q # işlemlerine yönelik kaynakları tahmin eder.

Tahmin aracı kaynakları, Q # programlarında hata ayıklamaya yardımcı olmak için daha zengin bir ölçüm ve araç kümesi sunan [hisse izleyici simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)üzerine kurulmuştur.

## <a name="invoking-and-running-the-resources-estimator"></a>Kaynak tahmin aracı 'ı çağırma ve çalıştırma

Herhangi bir Q # işlemini çalıştırmak için kaynaklar tahmin Aracı ' nı kullanabilirsiniz. Daha fazla ayrıntı için bkz. [bir Q # programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-resources-estimator-from-c"></a>C 'den kaynak tahmin aracı çağrılıyor # 

Diğer hedef makinelerde olduğu gibi, önce sınıfının bir örneğini oluşturur `ResourceEstimator` ve sonra bunu bir işlemin yönteminin ilk parametresi olarak iletirsiniz `Run` .

Sınıfından farklı olarak, sınıfı `QuantumSimulator` `ResourceEstimator` <xref:System.IDisposable> arabirimini uygulamaz ve bu nedenle onu bir deyime almanız gerekmez `using` .

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

Python kitaplığındaki [estimate_resources ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) yöntemini Içeri aktarılan Q # işlemiyle kullanın:

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a>Kaynak tahmin aracı 'ı komut satırından çağırma

Bir Q # programını komut satırından çalıştırırken, hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın `ResourcesEstimator` . Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır: 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a>Juptyer not defterlerinden kaynak tahmin aracı 'ı çağırma

Q # işlemini çalıştırmak için IQ # Magic komutu [% tahminini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın.

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a>Tahmini verileri program aracılığıyla alma

TSV tablosuna ek olarak, çalıştırma sırasında tahmini kaynakları kaynak Estimator özelliği aracılığıyla programlı bir şekilde alabilirsiniz `Data` . `Data`Özelliği `System.DataTable` iki sütunlu bir örnek sağlar: `Metric` ve `Sum` , ölçüm adlarına göre dizinlenir.

Aşağıdaki kod, `QubitClifford` `T` `CNOT` bir Q # işlemi tarafından kullanılan toplam ve işlem sayısının nasıl alınacağını ve yazdırılacağını gösterir:

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
|__Derinliğini__|Q # işlemi tarafından, hisse devdevlik derinliği için alt sınır. Varsayılan olarak, derinlik ölçümü yalnızca kapıları sayar `T` . Daha ayrıntılı bilgi için bkz. [derinlik sayacı](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).   |
|__Width__    |Q # işleminin çalıştırılması sırasında ayrılan en fazla qubit sayısı için alt sınır. Aynı anda hem __derinlik__ hem de __Genişlik__ alt sınırlarına ulaşmak mümkün olmayabilir.  |
|__Borrodilimlerin genişliği__    |Q # işlemi içinde ödünç alınan en fazla qubits sayısı.  |

## <a name="providing-the-probability-of-measurement-outcomes"></a>Ölçüm sonuçları olasılığını sağlama

<xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> Ölçüm işleminin beklenen olasılığı hakkında bilgi sağlamak için ad alanından ' i kullanabilirsiniz. Daha fazla bilgi için bkz. [hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)

## <a name="see-also"></a>Ayrıca bkz.

- [Hisse izi izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Hisse Toffoli simülatör](xref:microsoft.quantum.machines.toffoli-simulator)
- [Hisse dolu durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) 