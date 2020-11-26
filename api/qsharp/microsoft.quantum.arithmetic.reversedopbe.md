---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBE
title: ReversedOpBE işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBE
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 3c39a90ed4b5df09b90d8b5020d8b824285b50eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222329"
---
# <a name="reversedopbe-function"></a>ReversedOpBE işlevi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Büyük endian girişi alan bir işlem verildiğinde, küçük endian girişi alan yeni bir işlem döndürür.

```qsharp
function ReversedOpBE (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)
```


## <a name="input"></a>Giriş

### <a name="op--bigendian--unit"></a>Op: [bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Girişi geri çevrilme işlemi.



## <a name="output--littleendian--unit"></a>Çıkış: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Girişini küçük endian kaydı olarak kabul eden yeni bir işlem.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. aritmetik. ApplyReversedOpBE](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBE)
- [Microsoft. hisse. aritmetik. ReversedOpBEA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [Microsoft. hisse. aritmetik. ReversedOpBEC](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [Microsoft. hisse. aritmetik. ReversedOpBECA](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)