---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858154"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir ilgilendiğiniz işleci bir ile kodluyor `BlockEncoding` .

Bu `BlockEncoding` , bazı işleci kodlayan bir Unitary $U = P\cdot V\cdot P ^ \dağılım $ oluşturur $H = \ sum_ {j} | \ alpha_j | U_j $ ilgi çekici bir şekilde oluşturulur. Genellikle $P $, $P {0} \_ \tusa = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ ve $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $ gibi bir durum hazırlama birimiyiydir.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="statepreparation--t--unit--is-adj--ctl"></a>Statehazırlama: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bazı hedef durumları hazırlayan bir Unitary $P $.


### <a name="selector--ts--unit--is-adj--ctl"></a>seçici: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

$H $ 'ın bileşen unitları 'nı kodlayan bir Unitary $V $.



## <a name="output--ts--unit--is-adj--ctl"></a>Çıkış: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir Unitary $U $, yazmaçlara `a` ve `s` Bu blok-kodlar $H $ $U ve bu da < \hanger = U $ karşılar.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="s"></a>Üreticinin



## <a name="remarks"></a>Açıklamalar

Bu `BlockEncoding` uygulama, bunun özelliklerini verir `BlockEncodingReflection` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. hisse. simülasyon. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)