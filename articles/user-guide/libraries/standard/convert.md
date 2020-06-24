---
title: 'Q # standart kitaplıklarında tür dönüştürmeleri'
description: 'Q # standart kitaplıklarında ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275743"
---
# <a name="type-conversions"></a>Tür Dönüştürmeleri #

S #, **türü kesin belirlenmiş** bir dildir.
Özellikle, Q # ayrı türler arasında örtük olarak atama yapmaz. Örneğin, `1 + 2.0` geçerli bir Q # ifadesi değil.
Bunun yerine, Q # belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.

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

Son olarak, Q # standart kitaplığı, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> .
Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
