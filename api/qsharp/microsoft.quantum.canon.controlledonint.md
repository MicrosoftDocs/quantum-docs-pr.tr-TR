---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controltadonınt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207267"
---
# <a name="controlledonint-function"></a>Controltadonınt işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan bir Unitary işleci döndürür.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="numberstate--int"></a>numberState: [Int](xref:microsoft.quantum.lang-ref.int)

Pozitif tamsayı.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Unitary işleci.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

`oracle`Denetim kayıt durumu sayı durumuna karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işleci `numberState` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.