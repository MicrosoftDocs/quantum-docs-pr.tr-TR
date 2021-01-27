---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements
title: PurifiedMixedStateRequirements işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateRequirements
qsharp.summary: Returns the total number of qubits that must be allocated in order to apply the operation returned by @"microsoft.quantum.preparation.purifiedmixedstate".
ms.openlocfilehash: 6ddb48ba66eea87a07d515ff791bfb34f2d98b76
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856825"
---
# <a name="purifiedmixedstaterequirements-function"></a>PurifiedMixedStateRequirements işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tarafından döndürülen işlemi uygulamak için ayrılması gereken toplam qubits sayısını döndürür @"microsoft.quantum.preparation.purifiedmixedstate" .

```qsharp
function PurifiedMixedStateRequirements (targetError : Double, nCoefficients : Int) : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
```


## <a name="input"></a>Giriş

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef hata $ \ Epsilon $.


### <a name="ncoefficients--int"></a>Nkatsayıları: [Int](xref:microsoft.quantum.lang-ref.int)

Karma durum hazırlanırken belirtiedilecek katsayıların sayısı.



## <a name="output--mixedstatepreparationrequirements"></a>Çıkış: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)

Toplam olarak kaç qubit gerekli olduğu ve işlev tarafından kullanılan tüm dizin ve çöp kayıtları için bir açıklama @"microsoft.quantum.preparation.purifiedmixedstate" .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)