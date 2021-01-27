---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850449"
---
# <a name="applytotail-operation"></a>ApplyToTail işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine uygular.

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

En son uygulanacak hedefler dizisi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="example"></a>Örnek

Aşağıdaki Q # parçacıkları eşdeğerdir:

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. hisse. Canon. ApplyTo, c](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft. hisse. Canon. Applytobir CA](xref:Microsoft.Quantum.Canon.ApplyToTailCA)