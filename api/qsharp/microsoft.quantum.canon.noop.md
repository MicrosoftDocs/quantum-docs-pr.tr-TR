---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205975"
---
# <a name="noop-operation"></a>NoOp işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir bağımsız değişkende kimlik işlemini (No-Op) gerçekleştirir.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
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