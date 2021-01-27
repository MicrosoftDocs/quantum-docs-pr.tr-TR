---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Olgu işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853316"
---
# <a name="fact-function"></a>Olgu işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Klasik koşulun true olduğunu bildirir.

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--bool"></a>gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)

Belirtilecek koşul.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Klasik koşulun yanlış olması durumunda yazdırılacak hata iletisi dizesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Aşağıdaki Q # parçacığı başarısız olur:

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. tanılama. çelişme](xref:Microsoft.Quantum.Diagnostics.Contradiction)