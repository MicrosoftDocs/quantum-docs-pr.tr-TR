---
title: Hisse geliştirme seti tam durum simülatörü | Microsoft Docs
description: Microsoft 'un hisse geliştirme seti tam durum simülatörünü genel bakış
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: ab0e65765d27e301a59948d7c02105a523022e68
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184687"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Hisse geliştirme seti tam durum simülatörü

Hisse geliştirme seti, Microsoft Research 'tan [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) ile benzer bir tam durum hisse Benzetici sağlar.
Bu Benzetici, bilgisayarınızda Q # dilinde yazılan hisse algoritmaları yürütmek ve hatalarını ayıklamak için kullanılabilir.

Bu hisse Benzetici, `QuantumSimulator` sınıfı aracılığıyla sunulur. Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve bunu, diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse `Run` yöntemine geçirin:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator` sınıfı <xref:System.IDisposable>uygular, bu nedenle simülatör örneği artık kullanılmıyordu `Dispose` yöntemi çağrılmalıdır. Bunu yapmanın en iyi yolu, simülatörü Yukarıdaki örnekte olduğu gibi bir `using` ifadesine sarmalıdır.

## <a name="seed"></a>Çekirdek

`QuantumSimulator`, hisse rastlılığını taklit etmek için rastgele bir sayı Oluşturucu kullanır. Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur. Bu, `randomNumberGeneratorSeed` parametresi aracılığıyla `QuantumSimulator`oluşturucusunda rastgele numara Oluşturucu için bir çekirdek sağlanarak gerçekleştirilebilir:

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>Akışları

`QuantumSimulator`, gereken doğrusal algeköşeli paralel hale getirmek için [OpenMP](http://www.openmp.org/) kullanır. Varsayılan olarak OpenMP, tüm kullanılabilir donanım iş parçacıklarını kullanır, bu da az sayıda qubit içeren programların, gerçek işi dyacağı için gereken koordinasyonuna yavaş çalışacağı anlamına gelir. Bu, ortam değişkeni `OMP_NUM_THREADS` küçük bir sayı ayarlanarak düzeltilebilir. En çok kaba bir kural olarak, 1 iş parçacığı yaklaşık 4 qubit 'e kadar iyidir ve daha sonra, bu, algoritmanız için büyük ölçüde bağımlı olsa da, qubit başına ek bir iş parçacığı iyidir.

