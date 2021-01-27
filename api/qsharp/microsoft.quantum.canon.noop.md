---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 45f3c8c9d4bae8ac8f7f60c4e4f8ead5d92e7c00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852403"
---
# <a name="noop-operation"></a>NoOp işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir bağımsız değişkende kimlik işlemini (No-Op) gerçekleştirir.

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

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