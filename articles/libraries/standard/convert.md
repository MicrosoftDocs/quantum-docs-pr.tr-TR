---
title: 'Q # standart kitaplıkları-tür dönüştürmeleri | Microsoft Docs'
description: 'Q # standart kitaplıkları-tür dönüştürmeleri'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184483"
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
