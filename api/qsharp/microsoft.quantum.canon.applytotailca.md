---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: Applytobir CA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841192"
---
# <a name="applytotailca-operation"></a>Applytobir CA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine uygular.

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

En son uygulanacak hedefler dizisi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToTail](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft. hisse. Canon. ApplyToTailA](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [Microsoft. hisse. Canon. ApplyTo, c](xref:Microsoft.Quantum.Canon.ApplyToTailC)