---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Compareusingripptago işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223468"
---
# <a name="compareusingripplecarry-operation"></a>Compareusingripptago işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu işlem, qubits 'in bir yazmacından temsil edilen bir tamsayı başka bir tamsayıdır daha büyükse, bir çıkış qubit üzerine bir XOR sonucu uygulayarak sınar.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

İki tamsayı verildiğinde `x` ve `y` eşit boyutlu qubit Yazmaçları içinde depolanan bu işlem, karşılayıp karşılamadığını denetler `x > y` . True ise, 1 çıkış qubit XORed. Aksi halde, 0 bir çıkış qubit içine XORed.
Diğer bir deyişle, bu işlem Unitary $ $ \begin{hizalaması} U\ket {x} \ ayraç {y} \ demet {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} tarafından temsil edilebilir.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="x--littleendian"></a>x: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

`LittleEndian`Bir qubit kasada saklanan biçimde Karşılaştırılacak ilk numara.


### <a name="y--littleendian"></a>y: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bir qubit kasada saklanan şekilde karşılaştırılan ikinci sayı `LittleEndian` .


### <a name="output--qubit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)

$X>y $ karşılaştırma sonucunu depolayan qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- Yeni bir hisse Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184