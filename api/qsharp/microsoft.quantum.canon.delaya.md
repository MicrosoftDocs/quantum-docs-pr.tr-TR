---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207148"
---
# <a name="delaya-operation"></a>DelayA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir gecikmeyle belirli bir işlem uygular.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a>Açıklama

Bir işlem ve bu işlem için bir giriş verildiğinde, ek bir giriş sağlandıktan sonra işlemi uygular.
Özellikle, ifade `Delay(op, arg, _)` çağrıldığında için geçerli olan bir işlemdir `op` `arg` .
İfade `Delay(op,arg,_)` , uygulamasını gecikmeye izin verir `op` .

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Uygulanacak bir işlem.


### <a name="arg--t"></a>bağımsız değişken: 'T

İşlemin uygulandığı giriş.


### <a name="aux--unit"></a>Aux: [birim](xref:microsoft.quantum.lang-ref.unit)

Kısmi uygulama kullanarak işlemin uygulamasını geciktirmek için kullanılan bağımsız değişken.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Gecikecek işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. hisse. Canon. Gecikmeli](xref:Microsoft.Quantum.Canon.Delayed)