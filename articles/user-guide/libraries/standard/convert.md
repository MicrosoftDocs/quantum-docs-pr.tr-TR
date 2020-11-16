---
title: 'Standart kitaplıklarda tür dönüştürmeleri Q#'
description: 'Standart kitaplıklarda ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin Q# .'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691114"
---
# <a name="type-conversions"></a><span data-ttu-id="53b25-103">Tür Dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="53b25-103">Type Conversions</span></span> #

<span data-ttu-id="53b25-104">Q#**türü kesin belirlenmiş** bir dildir.</span><span class="sxs-lookup"><span data-stu-id="53b25-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="53b25-105">Özellikle Q# ayrı türler arasında örtük olarak atama yapmaz.</span><span class="sxs-lookup"><span data-stu-id="53b25-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="53b25-106">Örneğin, `1 + 2.0` geçerli bir Q# ifade değil.</span><span class="sxs-lookup"><span data-stu-id="53b25-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="53b25-107">Bunun yerine, Q# belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="53b25-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="53b25-108">Örneğin, bir <xref:Microsoft.Quantum.Core.Length> çıkış türüne sahiptir `Int` , bu nedenle çıktısının bir `Double` kayan nokta ifadesinin parçası olarak kullanılabilmesi için önce bir öğesine dönüştürülmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="53b25-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="53b25-109">Bu, işlevi kullanılarak yapılabilir <xref:Microsoft.Quantum.Convert.IntAsDouble> :</span><span class="sxs-lookup"><span data-stu-id="53b25-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="53b25-110"><xref:Microsoft.Quantum.Convert>Ad alanı,,,, ve gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar `Int` `Double` `BigInt` `Result` `Bool` :</span><span class="sxs-lookup"><span data-stu-id="53b25-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="53b25-111"><xref:Microsoft.Quantum.Convert>Ad alanı, `FunctionAsOperation` işlevleri yeni işlemlere dönüştüren gibi bazı daha bazı Exotic dönüşümler de sağlar `'T -> 'U` `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="53b25-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="53b25-112">Son olarak, Q# standart kitaplık, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="53b25-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="53b25-113">Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="53b25-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
