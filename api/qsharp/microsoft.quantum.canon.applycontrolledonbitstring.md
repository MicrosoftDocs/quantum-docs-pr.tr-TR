---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontroltadonbitstring işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 82adc74e23e1d50cb6436176a973fdd1a0eeb3bd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841940"
---
# <a name="applycontrolledonbitstring-operation"></a>Applycontroltadonbitstring işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hedef kayıt üzerinde, belirli bir bit maskesi tarafından belirtilen bir duruma göre denetlenen bir Unitary işlemi uygular.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="bits--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Hedef kaydına uygulanacak Unitary işlemi.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Uygulamasını denetleyen bir hisse kayıt `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Giriş olarak geçirilecek hedef kayıt `oracle` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Tarafından verilen model `bits` öğesinden daha kısa olabilir `controlRegister` , bu durumda ek denetim qugeler yok sayılır (yani, $ \grex {0} veya $ \ket $ üzerinde denetlenmez {1} ).
`bits`Daha uzunsa `controlRegister` bir hata oluşur.

Örneğin, `bits = [0,1,0,0,1]` `oracle` ancak yalnızca `controlRegister` $ \ ayraç {0} \ ayraç {1} {0} {0} \ ayraç {1} \ ayraç \ kutusunda ise geçerli olur.