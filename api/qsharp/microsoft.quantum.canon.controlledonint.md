---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controltadonınt işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728807"
---
# <a name="controlledonint-function"></a>Controltadonınt işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan bir Unitary işleci döndürür.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="numberstate--int"></a>numberState: [Int](xref:microsoft.quantum.lang-ref.int)

Pozitif tamsayı.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

Unitary işleci.



## <a name="output--qubitt--unit-adj--ctl"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

`oracle`Denetim kayıt durumu sayı durumuna karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işleci `numberState` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.