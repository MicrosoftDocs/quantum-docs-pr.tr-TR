---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Compareusingripptago işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843282"
---
# <a name="compareusingripplecarry-operation"></a>Compareusingripptago işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bu işlem, qubits 'in bir yazmacından temsil edilen bir tamsayı başka bir tamsayıdır daha büyükse, bir çıkış qubit üzerine bir XOR sonucu uygulayarak sınar.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

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