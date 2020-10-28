---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Çelişme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727284"
---
# <a name="contradiction-function"></a>Çelişme işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Klasik koşulun yanlış olduğunu bildirir.

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--bool"></a>gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)

Belirtilecek koşul.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Klasik koşulun doğru olması durumunda yazdırılacak hata iletisi dizesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. olgu](xref:Microsoft.Quantum.Diagnostics.Fact)