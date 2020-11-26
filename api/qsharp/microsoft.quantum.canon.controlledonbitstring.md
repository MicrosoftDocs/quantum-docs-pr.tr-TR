---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: Controltadonbitstring işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216668"
---
# <a name="controlledonbitstring-function"></a>Controltadonbitstring işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetim yazmacı durumu belirtilen bir bit maskesine karşılık geliyorsa, hedef kayıt üzerinde Oracle uygulayan Unitary işlemini döndürür.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Açıklama

Bu işlevin çıktısı, bir Unitary dönüşümle temsil edilebilir bir işlemdir $U $ \begin{hizalaması} U \ket{b_0 b_1 \cnoktalar b_ {n-1}} \ket{\psı} = \ket{b_0 b_1 \cnoktalar b_ {n-1}} \otimes \begin{Cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cnoktalar b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psı} & \textrm{otherwise} \end{Cases}, \end{hizalaması}; burada $V $ işlemin eylemini temsil eden bir Unitary dönüşümtür `oracle` .

## <a name="input"></a>Giriş

### <a name="bits--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Üzerinde verilen Unitary işleminin kontrol edilecek bit dizesi.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Hedef kaydına uygulanacak Unitary işlemi.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

`oracle`Denetim kayıt durumu bit maskesine karşılık geliyorsa, hedef kayıt üzerinde geçerli olan Unitary işlemi `bits` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Tarafından verilen model `bits` öğesinden daha kısa olabilir `controlRegister` , bu durumda ek denetim qugeler yok sayılır (yani, $ \grex {0} veya $ \ket $ üzerinde denetlenmez {1} ).
`bits`Daha uzunsa `controlRegister` bir hata oluşur.

Bir Boole dizisi `bits` ve Unitary işlemi verildiğinde `oracle` , bu işlevin çıktısı aşağıdaki adımları gerçekleştiren bir işlemdir:

* `X`öğesinin öğesine karşılık gelen denetim yazmacın her bir qubit öğesine bir işlem uygulayın `false` `bits` .
* `Controlled oracle`Denetim ve hedef Yazmaçları için geçerlidir;
* `X` `false` `bits` denetim kaydını özgün durumuna döndürmek için, tekrar öğesine karşılık gelen denetim yazmacın her bir qubit öğesine bir işlem uygulayın.

Functor çıkışı, `Controlled` öğesinin nereden eşit olduğu özel bir durumdur `ControlledOnBitString` `bits` `[true, ..., true]` .