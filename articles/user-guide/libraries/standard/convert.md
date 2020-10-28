---
title: Standart kitaplıklarda tür dönüştürmeleri Q#
description: Standart kitaplıklarda ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin Q# .
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691114"
---
# <a name="type-conversions"></a>Tür Dönüştürmeleri #

Q#**türü kesin belirlenmiş** bir dildir.
Özellikle Q# ayrı türler arasında örtük olarak atama yapmaz. Örneğin, `1 + 2.0` geçerli bir Q# ifade değil.
Bunun yerine, Q# belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.

Örneğin, bir <xref:Microsoft.Quantum.Core.Length> çıkış türüne sahiptir `Int` , bu nedenle çıktısının bir `Double` kayan nokta ifadesinin parçası olarak kullanılabilmesi için önce bir öğesine dönüştürülmesi gerekir.
Bu, işlevi kullanılarak yapılabilir <xref:Microsoft.Quantum.Convert.IntAsDouble> :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:Microsoft.Quantum.Convert>Ad alanı,,,, ve gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar `Int` `Double` `BigInt` `Result` `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:Microsoft.Quantum.Convert>Ad alanı, `FunctionAsOperation` işlevleri yeni işlemlere dönüştüren gibi bazı daha bazı Exotic dönüşümler de sağlar `'T -> 'U` `'T => 'U` .

Son olarak, Q# standart kitaplık, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
