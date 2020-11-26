---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 2cacac14ad6e5003f1a50d9b84c4e0f96950dd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207930"
---
# <a name="applytotaila-operation"></a>ApplyToTailA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine uygular.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Açıklama

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

En son uygulanacak hedefler dizisi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. hisse. Canon. ApplyTo, c](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. hisse. Canon. Applytobir CA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)