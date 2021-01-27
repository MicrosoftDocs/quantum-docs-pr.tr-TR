---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 0c1626c788215181b5ed45dc98bed928b5e4848a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843819"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>ApplyInnerTTKAdderWithoutCarry işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ripptacarryaddernocarryttk işlemi için iç Toplama işlevini uygular. Bu, tam Adder oluşturmak için dıştaki işlemle Birleşik işlem olan iç işlemdir.

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç birinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ikinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.

## <a name="references"></a>Başvurular

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530