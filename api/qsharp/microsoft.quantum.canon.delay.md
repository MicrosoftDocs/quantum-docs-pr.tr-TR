---
uid: Microsoft.Quantum.Canon.Delay
title: Gecikme işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728765"
---
# <a name="delay-operation"></a>Gecikme işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir gecikmeyle belirli bir işlem uygular.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Açıklama

Bir işlem ve bu işlem için bir giriş verildiğinde, ek bir giriş sağlandıktan sonra işlemi uygular.
Özellikle, ifade `Delay(op, arg, _)` çağrıldığında için geçerli olan bir işlemdir `op` `arg` .
İfade `Delay(op,arg,_)` , uygulamasını gecikmeye izin verir `op` .

## <a name="input"></a>Giriş

### <a name="op--t--u"></a>Op: 'T => ' U 

Uygulanacak bir işlem.


### <a name="arg--t"></a>bağımsız değişken: 'T

İşlemin uygulandığı giriş.


### <a name="aux--unit"></a>Aux: [birim](xref:microsoft.quantum.lang-ref.unit)

Kısmi uygulama kullanarak işlemin uygulamasını geciktirmek için kullanılan bağımsız değişken.



## <a name="output--u"></a>Çıkış: ' U



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Gecikecek işlemin giriş türü.
### <a name="u"></a>' U

Gecikecek işlemin dönüş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. hisse. Canon. DelayA](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. hisse. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. hisse. Canon. Gecikmeli](xref:Microsoft.Quantum.Canon.Delayed)