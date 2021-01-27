---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: ef92e517ae40e76c94aff1121c78ece9985109fc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857719"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir ilgilendiğiniz işleci bir ile kodluyor `BlockEncodingReflection` .

Bu `BlockEncodingReflection` , bazı işleci kodlayan bir Unitary $U = P\cdot V\cdot P ^ \dağılım $ oluşturur $H = \ sum_ {j} | \ alpha_j | U_j $ ilgi çekici bir şekilde oluşturulur. Genellikle $P $, $P {0} \_ \tusa \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ ve $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $ gibi bir durum hazırlama birimiyıdır.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Giriş

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a>Statehazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bazı hedef durumları hazırlayan bir Unitary $P $.


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a>seçici: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

$H $ 'ın bileşen unitları 'nı kodlayan bir Unitary $V $.



## <a name="output--blockencodingreflection"></a>Çıkış: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Bir Unitary $U $, Yazmaçlarda `a` ve `s` Bu blok-kodlayan $H $ ve ' ^ {-1} = U $ $U karşılar.

## <a name="remarks"></a>Açıklamalar

Bu `BlockEncoding` uygulama, bunun özelliklerini verir `BlockEncodingReflection` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. hisse. simülasyon. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)