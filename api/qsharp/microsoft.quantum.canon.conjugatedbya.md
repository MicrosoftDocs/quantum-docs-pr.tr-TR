---
uid: Microsoft.Quantum.Canon.ConjugatedByA
title: Birleşik Gatedbya işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: 141c42d335add85103e16598264f781f32ab80fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840861"
---
# <a name="conjugatedbya-function"></a>Birleşik Gatedbya işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.

```qsharp
function ConjugatedByA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj)) : ('T => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

$V $ eşleniği için kullanılması gereken $U $ işlemi. $U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.


### <a name="inneroperation--t--unit--is-adj"></a>ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

İşlem $V $.



## <a name="output--t--unit--is-adj"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Eylemi Unitary $U ^ {\hanger} V U $ tarafından temsil edilen yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her iç ve dış işlemin işlem yapması için gereken hedefin türü.

## <a name="remarks"></a>Açıklamalar

Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Birleşik Gatedbya](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. hisse. Canon. Birleşik Gatedbyc](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. hisse. Canon. Birleşik Gatedbyca](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. hisse. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)