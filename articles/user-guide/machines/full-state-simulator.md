---
title: Tam durum simülatör
description: 'Q # programlarınızı Microsoft Quantum Development Kit tam durum Benzeticisinde çalıştırmayı öğrenin.'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 12/7/2017
ms.topic: article
uid: microsoft.quantum.machines.full-state-simulator
ms.openlocfilehash: f73abbc4366b003e4b22366ed83ca9c897737307
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275647"
---
# <a name="quantum-development-kit-full-state-simulator"></a>Hisse geliştirme seti tam durum simülatörü

Hisse geliştirme seti, Microsoft Research 'tan [Liq $ UI | \rangle $](http://stationq.github.io/Liquid/) ile benzer bir tam durum hisse Benzetici sağlar.
Bu Benzetici, bilgisayarınızda Q # dilinde yazılan hisse algoritmaları yürütmek ve hatalarını ayıklamak için kullanılabilir.

Bu hisse Benzetici, sınıfı aracılığıyla sunulur `QuantumSimulator` . Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve `Run` diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse işlem yöntemine geçirin:

```csharp
    using (var sim = new QuantumSimulator())
    {
        var res = myOperation.Run(sim).Result;
        ///...
    }
```

## <a name="idisposable"></a>IDisposable

`QuantumSimulator`Sınıfı uygular <xref:System.IDisposable> , bu nedenle `Dispose` Benzetici örneği artık kullanılmaması durumunda yöntem çağrılmalıdır. Bunu yapmanın en iyi yolu, simülatörünü `using` Yukarıdaki örnekte olduğu gibi bir deyime sarmalıdır.

## <a name="seed"></a>Çekirdek

, `QuantumSimulator` Hisse rastlılığını taklit etmek için rastgele bir sayı Oluşturucu kullanır. Sınama amacıyla, bazen belirleyici sonuçlar elde etmek yararlı olur. Bu, `QuantumSimulator` parametresi aracılığıyla kurucusundaki rastgele sayı üreticisi için bir çekirdek sağlanarak gerçekleştirilebilir `randomNumberGeneratorSeed` :

```csharp
    using (var sim = new QuantumSimulator(randomNumberGeneratorSeed: 42))
    {
        var res = myOperationTest.Run(sim).Result;
        ///...
    }
```

## <a name="threads"></a>İş Parçacıkları

, `QuantumSimulator` Gereken doğrusal algeköşeli paralel hale getirmek Için [OpenMP](http://www.openmp.org/) kullanır. Varsayılan olarak, OpenMP kullanılabilir olan tüm donanım iş parçacıklarını kullanır. Böylelikle, gereken koordinasyon asıl işi küçülteceği için az sayıda qubit’i olan programlar sıkça yavaş çalışır. Bu, ortam değişkeni `OMP_NUM_THREADS` küçük bir sayı olarak ayarlanarak düzeltilebilir. Üstünkörü bir temel kural olarak, 1 iş parçacığı yaklaşık 4 qubit için uygundur ve her qubit başına bir tane ek iş parçacığı iyi bir sonuç verir. Ancak, bu kullandığınız algoritmaya yüksek oranda bağlıdır.

