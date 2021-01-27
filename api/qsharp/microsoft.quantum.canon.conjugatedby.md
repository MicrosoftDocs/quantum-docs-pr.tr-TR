---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: Birleşik Gatedby işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c11e6b2cc97e682bf4fe266997f60ce69e87ba96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840870"
---
# <a name="conjugatedby-function"></a>Birleşik Gatedby işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen dış ve iç işlemler, dış işlemin iç işlemini sağlayan yeni bir işlem döndürür.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Giriş

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

$V $ eşleniği için kullanılması gereken $U $ işlemi. $U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.


### <a name="inneroperation--t--unit"></a>ınneroperation: 'T => [birimi](xref:microsoft.quantum.lang-ref.unit) 

İşlem $V $.



## <a name="output--t--unit"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

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