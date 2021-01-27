---
uid: Microsoft.Quantum.Canon.Delay
title: Gecikme işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840649"
---
# <a name="delay-operation"></a>Gecikme işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir gecikmeyle belirli bir işlem uygular.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Description

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