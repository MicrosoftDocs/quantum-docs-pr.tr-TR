---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Compareusingripptago işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731618"
---
# <a name="compareusingripplecarry-operation"></a>Compareusingripptago işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Bu işlem, qubits 'in bir yazmacından temsil edilen bir tamsayı başka bir tamsayıdır daha büyükse, bir çıkış qubit üzerine bir XOR sonucu uygulayarak sınar.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
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



## <a name="references"></a>Referanslar

- Yeni bir hisse Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184