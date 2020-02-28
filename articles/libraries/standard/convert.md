---
title: 'Q # standart kitaplıklarında tür dönüştürmeleri'
description: 'Q # standart kitaplıklarında ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907809"
---
# <a name="type-conversions"></a>Tür dönüştürmeleri #

S #, **türü kesin belirlenmiş** bir dildir.
Özellikle, Q # ayrı türler arasında örtük olarak atama yapmaz. Örneğin, `1 + 2.0` geçerli bir Q # ifadesi değil.
Bunun yerine, Q # belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.

Örneğin, <xref:microsoft.quantum.core.length> bir `Int`çıkış türü vardır; bu nedenle, bir kayan nokta ifadesinin parçası olarak kullanılmadan önce çıktısının önce bir `Double` dönüştürmeniz gerekir.
Bu işlem, <xref:microsoft.quantum.convert.intasdouble> işlevi kullanılarak yapılabilir:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<xref:microsoft.quantum.convert> ad alanı, `Int`, `Double`, `BigInt`, `Result`ve `Bool`gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<xref:microsoft.quantum.convert> ad alanı, işlevleri `'T -> 'U` yeni `'T => 'U`işlemlere dönüştüren `FunctionAsOperation`gibi bazı daha bazı Exotic dönüşümler de sağlar.

Son olarak, Q # standart kitaplığı <xref:microsoft.quantum.math.complex> ve <xref:microsoft.quantum.arithmetic.littleendian>gibi bir dizi Kullanıcı tanımlı tür sağlar.
Bu türlerle birlikte, standart kitaplık <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>gibi işlevler sağlar:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
