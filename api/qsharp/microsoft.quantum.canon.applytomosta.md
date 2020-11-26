---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208508"
---
# <a name="applytomosta-operation"></a>ApplyToMostA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>Açıklama

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj"></a>Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applytoen](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. hisse. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. hisse. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)