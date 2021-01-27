---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841330"
---
# <a name="applytohead-operation"></a>ApplyToHead işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin ilk öğesine uygular.

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Head(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

İlki uygulanacak bir dizi hedef `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="example"></a>Örnek

Aşağıdaki Q # parçacıkları eşdeğerdir:

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToHeadA](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. hisse. Canon. ApplyToHeadC](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. hisse. Canon. ApplyToHeadCA](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)