---
uid: Microsoft.Quantum.Canon.ConjugatedByCA
title: Birleşik Gatedbyca işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByCA
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: df29bcf555026bceb13d6896db12e13671a49b9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728820"
---
# <a name="conjugatedbyca-function"></a>Birleşik Gatedbyca işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.

```qsharp
function ConjugatedByCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl)) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="outeroperation--t--unit-adj"></a>outerOperation: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması

$V $ eşleniği için kullanılması gereken $U $ işlemi. $U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.


### <a name="inneroperation--t--unit-adj--ctl"></a>ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

İşlem $V $.



## <a name="output--t--unit-adj--ctl"></a>Çıkış: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

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