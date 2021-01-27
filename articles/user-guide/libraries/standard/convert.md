---
title: Standart kitaplıklarda tür dönüştürmeleri Q#
description: Standart kitaplıklarda ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin Q# .
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858015"
---
# <a name="type-conversions"></a><span data-ttu-id="e763c-103">Tür Dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="e763c-103">Type Conversions</span></span> #

<span data-ttu-id="e763c-104">Q#**türü kesin belirlenmiş** bir dildir.</span><span class="sxs-lookup"><span data-stu-id="e763c-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="e763c-105">Özellikle Q# ayrı türler arasında örtük olarak atama yapmaz.</span><span class="sxs-lookup"><span data-stu-id="e763c-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="e763c-106">Örneğin, `1 + 2.0` geçerli bir Q# ifade değil.</span><span class="sxs-lookup"><span data-stu-id="e763c-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="e763c-107">Bunun yerine, Q# belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="e763c-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="e763c-108">Örneğin, bir <xref:Microsoft.Quantum.Core.Length> çıkış türüne sahiptir `Int` , bu nedenle çıktısının bir `Double` kayan nokta ifadesinin parçası olarak kullanılabilmesi için önce bir öğesine dönüştürülmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="e763c-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="e763c-109">Bu, işlevi kullanılarak yapılabilir <xref:Microsoft.Quantum.Convert.IntAsDouble> :</span><span class="sxs-lookup"><span data-stu-id="e763c-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="e763c-110"><xref:Microsoft.Quantum.Convert>Ad alanı,,,, ve gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar `Int` `Double` `BigInt` `Result` `Bool` :</span><span class="sxs-lookup"><span data-stu-id="e763c-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="e763c-111"><xref:Microsoft.Quantum.Convert>Ad alanı, `FunctionAsOperation` işlevleri yeni işlemlere dönüştüren gibi bazı daha bazı Exotic dönüşümler de sağlar `'T -> 'U` `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="e763c-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="e763c-112">Son olarak, Q# standart kitaplık, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:Microsoft.Quantum.Math.Complex> <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="e763c-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="e763c-113">Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="e763c-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
