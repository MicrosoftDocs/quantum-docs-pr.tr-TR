---
title: Tam durum hisse simülatör-hisse geliştirme seti
description: 'Q # programlarınızı Microsoft Quantum Development Kit tam durum benzeticisinde çalıştırmayı öğrenin.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: 563fdbd2a45461d112e4c46651eddd75c6fc3db2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871187"
---
# <a name="quantum-development-kit-qdk-full-state-simulator"></a>Hisse geliştirme seti (QDK) tam durum simülatör

QDK, yerel bilgisayarınızdaki bir hisse makinenizin benzetimini yapan tam bir durum simülatörü sağlar. En fazla 30 qubit kullanarak Q # dilinde yazılan hisse algoritmaları çalıştırmak ve hatalarını ayıklamak için tam durum simülatörü ' ni kullanabilirsiniz. Tam durum simülatörü, Microsoft Research 'ın [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) platformunda kullanılan hisse simülatcıya benzer.

## <a name="invoking-and-running-the-full-state-simulator"></a>Tam durum simülatörü çağırma ve çalıştırma

Sınıf aracılığıyla tam durum simülatörünü kullanıma sunacaksınız `QuantumSimulator` . Daha fazla ayrıntı için bkz. [bir Q # programını çalıştırma yolları](xref:microsoft.quantum.guide.host-programs).

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

Q # Python kitaplığındaki, içeri aktarılan Q # işlemiyle [Benzetim ()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) yöntemini kullanın:

```python
qubit_result = myOperation.simulate()
```

### <a name="invoking-the-simulator-from-the-command-line"></a>Komut satırından Benzetici çağırma

Bir Q # programını komut satırından çalıştırırken, tam durum simülatör varsayılan hedef makinedir. İsteğe bağlı olarak, istenen hedef makineyi belirtmek için **--simülatör** (veya **-s** Shortcut) parametresini kullanabilirsiniz. Aşağıdaki komutlardan her ikisi de tam durum simülatörü kullanarak bir program çalıştırır. 

```dotnetcli
dotnet run
dotnet run -s QuantumSimulator
```

### <a name="invoking-the-simulator-from-juptyer-notebooks"></a>Juptyer not defterlerinden simülatörü çağırma

Q # işlemini çalıştırmak için IQ # Magic komutu [% benzetimini](xref:microsoft.quantum.iqsharp.magic-ref.simulate) kullanın.

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

- [Hisse kaynağı tahmin aracı](xref:microsoft.quantum.machines.resources-estimator)
- [Hisse Toffoli simülatör](xref:microsoft.quantum.machines.toffoli-simulator)
- [Hisse izi izleme simülatörü](xref:microsoft.quantum.machines.qc-trace-simulator.intro)