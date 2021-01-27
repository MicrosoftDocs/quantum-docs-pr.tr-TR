---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontroltadonınt işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 499a25104742b2d03886065baad4d535ea92e83b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845109"
---
# <a name="applycontrolledonint-operation"></a>Applycontroltadonınt işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetim yazmacı durumu belirtilen pozitif tamsayıya karşılık geliyorsa, hedef kayıt üzerinde bir Unitary işlemi uygular.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="numberstate--int"></a>numberState: [Int](xref:microsoft.quantum.lang-ref.int)

İşlemin denetlenmesi gereken negatif olmayan bir tamsayı `oracle` .


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

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