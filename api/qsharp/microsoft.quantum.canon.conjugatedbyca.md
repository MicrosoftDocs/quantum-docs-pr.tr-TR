---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: Birleşik Gatedbyca işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: acd5a9f796f751b9c9c374d841e80de9286fcd24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207318"
---
# <a name="conjugatedbyca-function"></a>Birleşik Gatedbyca işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

$V $ eşleniği için kullanılması gereken $U $ işlemi. $U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

İşlem $V $.



## <a name="output--t--unit--is-adj--ctl"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

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