---
uid: Microsoft.Quantum.Canon.ApplyWithCA
title: ApplyWithCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithCA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: a5ce7dc5ddfbb2fc06743d36614129c371850da2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841138"
---
# <a name="applywithca-operation"></a>ApplyWithCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki işlem verildiğinde, diğerini diğeri ile birlikte uygular.

```qsharp
operation ApplyWithCA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj + Ctl), target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Sırasıyla Unitary işleçleri $U $ ve $V $ tarafından tanımlanan iki işlem, bu dosyaları ^ {\abger} V U $ $U dizisine uygular. Diğer bir deyişle, bu işlem $U $ ile $V $ Birleşik tarafından verilen Unitary işlecini uygular.

## <a name="input"></a>Giriş

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

$V $ eşleniği için kullanılması gereken $U $ işlemi. $U $ dış işleminin adjointable olması gerektiğini, ancak denetlenebilir olması gerektiğini unutmayın.


### <a name="inneroperation--t--unit--is-adj--ctl"></a>ınneroperation: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

İşlem $V $.


### <a name="target--t"></a>Hedef: 'T

Dış ve iç işlemlere sağlanacak giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her iç ve dış işlemin üzerinde işlem gören hedef.

## <a name="remarks"></a>Açıklamalar

Dış işlemin her zaman adjointable olduğu varsayılır, ancak birleştirilmiş işlemin denetlenebilir olması için denetlenebilir olması gerekmez.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. hisse. Canon. ApplyWithA](xref:Microsoft.Quantum.Canon.ApplyWithA)
- [Microsoft. hisse. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)