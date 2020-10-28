---
uid: Microsoft.Quantum.Canon.ApplyControlledOnBitString
title: Applycontroltadonbitstring işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnBitString
qsharp.summary: Applies a unitary operation on the target register, controlled on a a state specified by a given bit mask.
ms.openlocfilehash: 7a054511bacff574e6f7e889ace048c78886cf91
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729674"
---
# <a name="applycontrolledonbitstring-operation"></a>Applycontroltadonbitstring işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Hedef kayıt üzerinde, belirli bir bit maskesi tarafından belirtilen bir duruma göre denetlenen bir Unitary işlemi uygular.

```qsharp
operation ApplyControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Giriş

### <a name="bits--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

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