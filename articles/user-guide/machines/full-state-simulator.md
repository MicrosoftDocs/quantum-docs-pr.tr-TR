---
title: Tam durum hisse simülatör-hisse geliştirme seti
description: Q#Programlarınızı Microsoft Quantum Development Kit tam durum benzeticisinde nasıl çalıştıracağınızı öğrenin.
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 632af681c5818ab7246c0f5849a8b8e716b570cb
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833374"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Hisse geliştirme seti (QDK) tam durum simülatör

QDK, yerel bilgisayarınızdaki bir hisse makinenizin benzetimini yapan tam bir durum simülatörü sağlar. En fazla 30 qubit kullanarak, içinde yazılmış olan hisse algoritmaları çalıştırmak ve hatalarını ayıklamak için tam durum simülatörü ' Q# ni kullanabilirsiniz. Tam durum simülatörü, Microsoft Research 'ın  [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformunda kullanılan hisse simülatcıya benzer.

## <a name="invoking-and-running-the-full-state-simulator"></a>Tam durum simülatörü çağırma ve çalıştırma

Sınıf aracılığıyla tam durum simülatörünü kullanıma sunacaksınız `QuantumSimulator` . Daha fazla bilgi için bkz. [ Q# Program çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).

### <a name="invoking-the-simulator-from-c"></a>C 'den simülatör çağrılıyor #

Sınıfın bir örneğini oluşturun `QuantumSimulator` ve sonra `Run` ek parametrelerle birlikte bir hisse işlem yöntemine geçirin.
```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

`QuantumSimulator`Sınıfı <xref:System.IDisposable> arabirimini uyguladığından, `Dispose` simülatör örneğine gerek duyduktan sonra yöntemini çağırmanız gerekir. Bunu yapmanın en iyi yolu, simülatör bildirimini ve işlemlerini yöntemi otomatik olarak çağıran bir [using](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/using-statement) ifadesiyle sarmalıdır `Dispose` .

### <a name="invoking-the-simulator-from-python"></a>Python 'dan simülatör çağrılıyor

Python kitaplığındaki [Benzetim ()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) yöntemini Q# içeri aktarılan işlemle birlikte kullanın Q# :

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Komut satırından Benzetici çağırma

Q#Komut satırından bir program çalıştırırken, tam durum simülatör varsayılan hedef makinedir. İsteğe bağlı olarak, istenen hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanabilirsiniz. Aşağıdaki komutlardan her ikisi de tam durum simülatörü kullanarak bir program çalıştırır. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Juptyer not defterlerinden simülatörü çağırma

Q#İşlemi çalıştırmak için I Magic komutu [% benzetimini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın Q# .

```
%simulate myOperation
```
## <a name="seeding-the-simulator"></a>Simülatör dengeli

Varsayılan olarak, tam durum simülatörü, hisse miktarı benzetimi için rastgele bir sayı Oluşturucu kullanır. Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur. Bir C# programında, parametresi aracılığıyla oluşturucuda rastgele numara Oluşturucu için bir çekirdek sağlayarak bunu yapabilirsiniz `QuantumSimulator` `randomNumberGeneratorSeed` .

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="configuring-threads"></a>İş parçacıklarını yapılandırma

Tam durum simülatör, gereken doğrusal algeköşeli paralel hale getirmek için [OpenMP](http://www.openmp.org/) kullanır. Varsayılan olarak, OpenMP, en az sayıda qubit olan programlar, gerçek işi dide gereken koordinasyon nedeniyle genellikle yavaş çalıştığı anlamına gelen tüm kullanılabilir donanım iş parçacıklarını kullanır. Bu ayarı, ortam değişkenini `OMP_NUM_THREADS` küçük bir sayı olarak ayarlayarak giderebilirsiniz. Thumb kuralı olarak, bir iş parçacığını en fazla dört qubit ve daha sonra qubit başına bir ek iş parçacığı yapılandırın. Algoritmasına göre değişkeni ayarlamanız gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Kuantum kaynak tahmin aracı](xref:microsoft.quantum.machines.resources-estimator)
- [Kuantum Toffoli simülatörü](xref:microsoft.quantum.machines.toffoli-simulator)
- [Hisse izi izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)