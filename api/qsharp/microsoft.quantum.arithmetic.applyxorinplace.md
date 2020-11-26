---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210123"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir klasik tamsayı ile bir qubits yazmacı ile temsil edilen bir tamsayı arasında bit düzeyinde XOR işlemi uygular.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`X`Bir tamsayının 1 bite göre küçük endian kaydındaki işlemleri qubits 'e uygular.

`value`Bir ' a göre belirlememize ve ' de bir işaretsiz tamsayı olmasına izin verin `target` , ardından `InPlaceXorLE` Şu eşleme tarafından verilen bir işlem gerçekleştirir: $ \ket{y}\rightarrow \ket{y\oplus a} $, burada $ \oplus $ bit DÜZEYINDE dışlamalı veya işleçtir.

## <a name="input"></a>Giriş

### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Negatif olmayan bir tamsayı.


### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Küçük endian kodlamasıyla depolamak için kullanılan bir hisse kayıt `value` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

