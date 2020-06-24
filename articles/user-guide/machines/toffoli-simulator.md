---
title: Hisse geliştirme seti Toffoli simülatör
description: Milyonlarca qubitle kullanılabilecek özel bir amaç simülatörü olan Microsoft QDK Toffoli benzeticileri hakkında bilgi edinin.
author: alan-geller
ms.author: ageller@microsoft.com
ms.date: 01/16/2019
ms.topic: article
uid: microsoft.quantum.machines.toffoli-simulator
ms.openlocfilehash: 8a29caaa0fa058600a74e7d130e644374cbfa19c
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276026"
---
# <a name="quantum-development-kit-toffoli-simulator"></a>Hisse geliştirme seti Toffoli simülatör

Hisse geliştirme seti, X, CNOT ve çok kontrollü X hisse malarıyla (tüm klasik mantık ve hesaplamalar kullanılabilir) sınırlı olan hisse cıcılarının benzetimini yapan bir Toffoli simülasyonu sağlar.

Toffoli simülatör, [tam durum simülatörü](xref:microsoft.quantum.machines.full-state-simulator)tarafından çok daha kısıtlanıyor olsa da, bu çok daha fazla qubit benzetimi yapabilir.
Toffoli simülatörü milyonlarca qubitle birlikte kullanılabilir, ancak tam durum simülatörü genellikle yaklaşık 30 ' a sınırlanır.
Bilgisayarınızda Q # dilinde yazılmış sınırlı bir hisse algoritması kümesini yürütebilir ve hata ayıklaması yapabilir; Örneğin, Boole işlevlerini değerlendiren Oracles bu kapıları kullanılarak uygulanabilir ve bu nedenle test, bu simülatörü kullanan büyük sayıda qubit farklılık gösterir.

Bu hisse Benzetici, sınıfı aracılığıyla sunulur `ToffoliSimulator` .
Simülatörü kullanmak için, bu sınıfın bir örneğini oluşturun ve `Run` diğer parametrelerin geri kalanında birlikte yürütmek istediğiniz hisse işlem yöntemine geçirin:

```csharp
    var sim = new ToffoliSimulator();
    var res = myOperation.Run(sim).Result;
    ///...
```

## <a name="other-operations"></a>Diğer Işlemler

, `ToffoliSimulator` Ve gibi, `R` `Exp` ortaya çıkan işlem, `X` kimliğe veya kimliğe eşit olduğunda, ve gibi dağıtılmış Paulis 'leri destekler.

Ölçüm ve onaylama desteklenir, ancak yalnızca Pauli `Z` temelinde desteklenir.
Bazı ölçüm olasılığının her zaman 0 veya 1 olduğunu unutmayın; Toffoli benzeticisinde rastgele bir değer yoktur.

`DumpMachine`ve `DumpRegister` desteklenir.
Her ikisi de `Z` her bir qubit, satır başına bir qubit olmak üzere her bir qubit için geçerli olan durum

## <a name="qubitcount"></a>QubitCount

Varsayılan olarak, `ToffoliSimulator` 65.536 qubit için alan ayırır.
Algoritmanız bundan fazla gerektiriyorsa, oluşturucuya parametre için bir değer sağlayarak qubit sayısını değiştirebilirsiniz `qubitCount` .
Her ek qubit ek bir bellek gerektirir, bu nedenle ihtiyaç duyacağınız qubit sayısını fazla tahmin etmek için önemli bir maliyet yoktur.

Örneğin:

```csharp
    var sim = new ToffoliSimulator(qubitCount: 1000000);
    var res = myLargeOperation.Run(sim).Result;
```
