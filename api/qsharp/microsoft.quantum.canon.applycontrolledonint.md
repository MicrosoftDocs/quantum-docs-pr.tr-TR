---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontroltadonınt işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729671"
---
# <a name="applycontrolledonint-operation"></a>Applycontroltadonınt işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde bir Unitary işlemi uygular.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Giriş

### <a name="numberstate--int"></a>numberState: [Int](xref:microsoft.quantum.lang-ref.int)

İşlemin denetlenmesi gereken negatif olmayan bir tamsayı `oracle` .


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

Denetimli bir Unitary işlemi.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Uygulamasını denetleyen bir hisse kayıt `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Uygulanacağı kayıt `oracle` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Değeri, `numberState` küçük endian kodlamalı bir kodlama kullanılarak yorumlanır.

`numberState` en fazla $2 ^ \texttt{Length (controlRegister)}-$1 olmalıdır.
Örneğin, `numberState = 537` `oracle` yalnızca `controlRegister` $ \ket $ durumunda ise uygulandığı anlamına gelir {537} .