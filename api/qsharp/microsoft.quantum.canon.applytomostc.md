---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850554"
---
# <a name="applytomostc-operation"></a>ApplyToMostC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-ctl"></a>Op: 'T [] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applytoen](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. hisse. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. hisse. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)