---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLECA
title: ReversedOpLECA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLECA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: c058243db2b4cee3a72e025b084b4f98f7020a6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222074"
---
# <a name="reversedopleca-function"></a>ReversedOpLECA işlevi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Küçük endian girişi alan bir işlem verildiğinde, büyük endian girişi alan yeni bir işlem döndürür.

```qsharp
function ReversedOpLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--littleendian--unit--is-adj--ctl"></a>Op: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Girişi geri çevrilme işlemi.



## <a name="output--bigendian--unit--is-adj--ctl"></a>Çıkış: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Girişini büyük endian kaydı olarak kabul eden yeni bir işlem.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. ApplyReversedOpLECA](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLECA)
- [Microsoft. hisse. aritmetik. Smardoor](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [Microsoft. hisse. aritmetik. ReversedOpLEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [Microsoft. hisse. aritmetik. ReversedOpLEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)