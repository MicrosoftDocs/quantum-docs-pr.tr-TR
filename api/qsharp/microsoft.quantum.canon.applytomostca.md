---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841308"
---
# <a name="applytomostca-operation"></a>ApplyToMostCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

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
- [Microsoft. hisse. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)