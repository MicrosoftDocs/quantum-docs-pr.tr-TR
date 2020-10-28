---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727230"
---
# <a name="equalityfactr-function"></a>EqualityFactR işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Klasik bir sonuç değişkeninin beklenen değere sahip olduğunu onaylar.

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--__invalidresult__"></a>gerçek: __geçersiz <Result>__

Denetlenecek değişken.


### <a name="expected--__invalidresult__"></a>beklenen: __geçersiz <Result>__

Beklenen değer.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

