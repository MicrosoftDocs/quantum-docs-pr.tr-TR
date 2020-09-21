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
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835613"
---
# <a name="type-conversions"></a>Tür Dönüştürmeleri #

Q#**türü kesin belirlenmiş** bir dildir.
Özellikle Q# ayrı türler arasında örtük olarak atama yapmaz. Örneğin, `1 + 2.0` geçerli bir Q# ifade değil.
Bunun yerine, Q# belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.

Örneğin, bir <xref:microsoft.quantum.core.length> çıkış türüne sahiptir `Int` , bu nedenle çıktısının bir `Double` kayan nokta ifadesinin parçası olarak kullanılabilmesi için önce bir öğesine dönüştürülmesi gerekir.
Bu, işlevi kullanılarak yapılabilir <xref:microsoft.quantum.convert.intasdouble> :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert>Ad alanı,,,, ve gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar `Int` `Double` `BigInt` `Result` `Bool` :

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert>Ad alanı, `FunctionAsOperation` işlevleri yeni işlemlere dönüştüren gibi bazı daha bazı Exotic dönüşümler de sağlar `'T -> 'U` `'T => 'U` .

Son olarak, Q# standart kitaplık, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> .
Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
