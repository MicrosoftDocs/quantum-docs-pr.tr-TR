---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828269"
---
# <a name="formattedfailure-function"></a>FormattedFailure işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Anlamlı hata iletileriyle başarısız olmak için kullanılan iç işlev.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--t"></a>gerçek: 'T




### <a name="expected--t"></a>beklenen: 'T




### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Bu işlevin simülasyonu çalışma zamanları tarafından öykünmek üzere tasarlanmıştır. bu nedenle, biçimlendirilen çelişmeleri iletmeyi sağlamak için.