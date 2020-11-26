---
uid: Microsoft.Quantum.Canon.CControlledA
title: Ccontroltada işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207522"
---
# <a name="ccontrolleda-function"></a>Ccontroltada işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür. Yoksa `false` , hiçbir şey olmaz.
Değiştirici, `A` işlemin adjointable olduğunu gösterir.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Koşullu olarak uygulanacak bir işlem.



## <a name="output--boolt--unit--is-adj"></a>Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Klasik denetim biti doğru ise op olan yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Cdenetimli](xref:Microsoft.Quantum.Canon.CControlled)