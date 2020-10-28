---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 987e39577c3b736418234431ed7a915ae461f763
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728525"
---
# <a name="noop-operation"></a>NoOp işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir bağımsız değişkende kimlik işlemini (No-Op) gerçekleştirir.

```qsharp
operation NoOp<'T> (input : 'T) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem herhangi bir türde bir değer alır ve bir şey yapmaz.
Bu, bir işlem türü girişi beklendiğinde yararlı olabilir, ancak hiçbir işlem gerçekleştirilmez.
Örneğin, belirli bir hata düzeltmesi sendromu hata oluştuğunu gösteriyorsa, `NoOp<Qubit[]>` doğru kurtarma yordamı olabilir.
Benzer şekilde, bir işlem giriş olarak bir durum hazırlama yordamı beklediğinde, `NoOp<Qubit[]>` $ \ket{0 \cnoktalar 0} $ durumunu hazırlamak için kullanılabilir.

## <a name="input"></a>Giriş

### <a name="input--t"></a>Giriş: 'T

Yok sayılacak bir değer.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Neredeyse her durumda, için tür parametresinin `NoOp` açıkça belirtilmesi gerekir. Örneğin, `NoOp<Qubit>` ile aynıdır <xref:microsoft.quantum.intrinsic.i> .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Iç. I](xref:Microsoft.Quantum.Intrinsic.I)