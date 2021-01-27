---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843467"
---
# <a name="applyxorinplace-operation"></a>ApplyXorInPlace işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir klasik tamsayı ile bir qubits yazmacı ile temsil edilen bir tamsayı arasında bit düzeyinde XOR işlemi uygular.

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

`X`Bir tamsayının 1 bite göre küçük endian kaydındaki işlemleri qubits 'e uygular.

`value`Bir ' a göre belirlememize ve ' de bir işaretsiz tamsayı olmasına izin verin `target` , ardından `InPlaceXorLE` Şu eşleme tarafından verilen bir işlem gerçekleştirir: $ \ket{y}\rightarrow \ket{y\oplus a} $, burada $ \oplus $ bit DÜZEYINDE dışlamalı veya işleçtir.

## <a name="input"></a>Giriş

### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Negatif olmayan bir tamsayı.


### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Küçük endian kodlamasıyla depolamak için kullanılan bir hisse kayıt `value` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

