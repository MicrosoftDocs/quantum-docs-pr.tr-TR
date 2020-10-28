---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731527"
---
# <a name="greaterthan-operation"></a>GreaterThan işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Qubit Yazmaçları ile kodlanmış iki tamsayı arasında bir daha büyüktür karşılaştırması uygular ve karşılaştırmanın sonucuna göre bir hedef qubit alır.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>Açıklama

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

## <a name="references"></a>Referanslar

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haümü, MARI Roetteler, Kronysta M. Svore: "düzenleme Toffoli tabanlı modüler çarpma ile 2n + 2 qubit kullanma", 2016 https://arxiv.org/abs/1611.07995