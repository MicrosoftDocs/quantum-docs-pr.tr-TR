---
title: Hisse geliştirme seti Toffoli simülatör | Microsoft Docs
description: Microsoft 'un hisse alım geliştirme seti Toffoli simülatörü 'ne genel bakış
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 26940d1a8fe31f1035e2d23a68940cd999517c6b
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442358"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Hisse geliştirme seti Toffoli simülatör

Hisse geliştirme seti, X, CNOT ve çok kontrollü X hisse malarıyla (tüm klasik mantık ve hesaplamalar kullanılabilir) sınırlı olan hisse cıcılarının benzetimini yapan bir Toffoli simülasyonu sağlar.

Toffoli simülatör, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)tarafından çok daha kısıtlanıyor olsa da, bu çok daha fazla qubit benzetimi yapabilir.
Toffoli simülatörü milyonlarca qubitle birlikte kullanılabilir, ancak tam durum simülatörü genellikle yaklaşık 30 ' a sınırlanır.
Bilgisayarınızda Q # dilinde yazılmış sınırlı bir hisse algoritması kümesini yürütebilir ve hata ayıklaması yapabilir; Örneğin, Boole işlevlerini değerlendiren Oracles bu kapıları kullanılarak uygulanabilir ve bu nedenle test, bu simülatörü kullanan büyük sayıda qubit farklılık gösterir.

Bu hisse Benzetici, `ToffoliSimulator` sınıfı aracılığıyla sunulur.
Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve bunu, diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse `Run` yöntemine geçirin:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Diğer Işlemler

`ToffoliSimulator`, ortaya çıkan işlem `X` veya kimliğe eşit olduğunda, `R` ve `Exp`gibi döndürmeler ve üs dağıtılmış Paulis 'leri destekler.

Ölçüm ve onaylama desteklenir, ancak yalnızca Pauli `Z` temelinde desteklenir.
Bazı ölçüm olasılığının her zaman 0 veya 1 olduğunu unutmayın; Toffoli benzeticisinde rastgele bir değer yoktur.

`DumpMachine` ve `DumpRegister` desteklenir.
Her ikisi de her bir qubit için geçerli `Z`temel durumunu çıktı, her satıra bir qubit.

## <a name="qubitcount"></a>QubitCount

`ToffoliSimulator`, varsayılan olarak 65.536 qubit için alan ayırır.
Algoritmanız bundan fazla gerektiriyorsa, oluşturucuya `qubitCount` parametresi için bir değer sağlayarak qubit sayısını değiştirebilirsiniz.
Her ek qubit ek bir bellek gerektirir, bu nedenle ihtiyaç duyacağınız qubit sayısını fazla tahmin etmek için önemli bir maliyet yoktur.

Örnek:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
