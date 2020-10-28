---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727236"
---
# <a name="equalityfactl-function"></a>EqualityFactL işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Klasik bir BigInt değişkeninin beklenen değere sahip olduğunu onaylar.

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--bigint"></a>gerçek: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Denetlenecek sayı.


### <a name="expected--bigint"></a>beklenen: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Beklenen değer.


### <a name="message--string"></a>ileti: [dize](xref:microsoft.quantum.lang-ref.string)

Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

