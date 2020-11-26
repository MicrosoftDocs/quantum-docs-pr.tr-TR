---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201708"
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