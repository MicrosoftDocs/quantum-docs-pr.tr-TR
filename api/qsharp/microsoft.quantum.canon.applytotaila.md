---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729047"
---
# <a name="applytotaila-operation"></a>ApplyToTailA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi bir dizinin son öğesine uygular.

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>Açıklama

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Tail(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit-adj"></a>Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması

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