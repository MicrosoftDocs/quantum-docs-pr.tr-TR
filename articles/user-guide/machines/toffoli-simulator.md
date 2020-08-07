---
title: Hisse Toffoli simülatör-hisse geliştirme seti
description: Milyonlarca qubitle kullanılabilecek özel bir amaç simülatörü olan Microsoft QDK Toffoli benzeticileri hakkında bilgi edinin.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 6/25/2020
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8a981645703423856e667be7c3dccf5270a5885f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868109"
---
# <a name="quantum-development-kit-qdk-toffoli-simulator"></a>Hisse geliştirme seti (QDK) Toffoli simülatör

QDK Toffoli simülatörü, sınırlı bir kapsama sahip özel amaçlı bir Benzetici ve yalnızca `X` , `CNOT` ve çoklu denetimli `X` hisse operasyonlarını destekler. Tüm klasik mantık ve hesaplamalar kullanılabilir.

Toffoli simülatör, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)'nin işlevselliğinde daha kısıtlı olsa da, bu, en fazla qubit benzetimi yapabilmesinin avantajına sahiptir. Toffoli simülatörü milyonlarca qubit ile birlikte kullanılabilir, ancak tam durum simülatörü yaklaşık 30 qubitle sınırlıdır. Bu, örneğin, Boole işlevlerini değerlendiren Oracles ile, sınırlı desteklenen algoritmalar kümesi kullanılarak uygulanamazlar ve çok sayıda qubit üzerinde test edilebilir.

## <a name="invoking-the-toffoli-simulator"></a>Toffoli simülatörü çağırma

Toffoli simülatörünü sınıfı aracılığıyla kullanıma sunun `ToffoliSimulator` . Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-toffoli-simulator-from-c"></a>C Toffoli simülatörü çağırma #

Diğer hedef makinelerde olduğu gibi, önce `ToffoliSimulator` sınıfının bir örneğini oluşturup ardından bunu bir işlemin `Run` metodunun ilk parametresi olarak geçirirsiniz.

`QuantumSimulator` sınıfının aksine, `ToffoliSimulator` sınıfının <xref:System.IDisposable> arabirimini uygulamadığını ve bu nedenle bunu bir `using` deyimi içine almanız gerekmediğini unutmayın.

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

### <a name="invoking-the-toffoli-simulator-from-python"></a>Python 'dan Toffoli simülatörü çağırma

Python kitaplığındaki [toffoli_simulate ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) yöntemini içeri aktarılan Q# işlemle kullanın:

```python
qubit_result = myOperation.toffoli_simulate()
```

### <a name="invoking-the-toffoli-simulator-from-the-command-line"></a>Komut satırından Toffoli simülatörü çağırma

Q#Komut satırından bir program çalıştırırken, Toffoli simülatör hedef makinesini belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanın. Aşağıdaki komut Estimator kaynaklarını kullanarak bir program çalıştırır: 

```dotnetcli
dotnet run -s ToffoliSimulator
```

### <a name="invoking-the-toffoli-simulator-from-juptyer-notebooks"></a>Juptyer not defterlerinden Toffoli simülatörü çağırma

Q#İşlemi çalıştırmak için I Magic komutu [% Toffoli](xref:microsoft.quantum.iqsharp.magic-ref.toffoli) kullanın Q# .

```
%toffoli myOperation
```

## <a name="supported-operations"></a>Desteklenen işlemler

Toffoli simülatör şunları destekler:

* `R` `Exp` Ortaya çıkan işlem, `X` ya da kimlik matrisine eşit olduğunda, ve gibi geçen Paulis 'ler.
* Ölçüm ve [onaylama](xref:microsoft.quantum.diagnostics.assertmeasurement) işlemleri, ancak yalnızca Pauli `Z` temelinde. Ölçüm işleminin olasılığının her zaman **0** ya da **1**olduğunu unutmayın; Toffoli benzeticisinde rastgele bir değer yoktur.
* `DumpMachine`ve `DumpRegister` işlevleri.
Her iki işlev de `Z` her bir qubit, satır başına bir qubit olmak üzere, her bir qubit için geçerli

## <a name="specifying-the-number-of-qubits"></a>Qubits sayısını belirtme

Varsayılan olarak, bir `ToffoliSimulator` örnek 65.536 qubit için alan ayırır.
Algoritmanız bundan daha fazla qubit gerektiriyorsa, oluşturucuya parametresi için bir değer sağlayarak qubit sayısını belirtebilirsiniz `qubitCount` .
Her ek qubit yalnızca bir baytlık bellek gerektirir, bu nedenle ihtiyaç duyacağınız qubit sayısını fazla tahmin etmek için önemli bir maliyet yoktur.

Örnek:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```

## <a name="see-also"></a>Ayrıca bkz.

- [Hisse kaynağı Estimator](xref:microsoft.quantum.machines.resources-estimator)
- [Hisse Izi Izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [Hisse dolu durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator) 