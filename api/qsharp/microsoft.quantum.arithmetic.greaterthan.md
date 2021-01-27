---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846627"
---
# <a name="greaterthan-operation"></a>GreaterThan işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit Yazmaçları ile kodlanmış iki tamsayı arasında bir daha büyüktür karşılaştırması uygular ve karşılaştırmanın sonucuna göre bir hedef qubit alır.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

$X $ ve $y $, qubit, XS ve YS içinde kodlandığı iki tamsayının karşılaştırmadan kesinlikle daha büyük bir şekilde gerçekleştirir. $X y $ >, sonuç qubit çevrilcektir, aksi takdirde sonuç qubit, durumunu korur.

## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ilk tamsayıyı $x $.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Litttaendian qubit yazmaç ikinci tamsayıyı $y $.


### <a name="result--qubit"></a>Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)

$X > y $ olarak çevrilmiş tek qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

$X-y = (x ' + y) ' $ olan eli kullanır, burada ' ise birinin tamamlayıcı olduğunu gösterir.

## <a name="references"></a>Başvurular

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haümü, MARI Roetteler, Kronysta M. Svore: "düzenleme Toffoli tabanlı modüler çarpma ile 2n + 2 qubit kullanma", 2016 https://arxiv.org/abs/1611.07995