---
title: Standart kitaplıklarda tür dönüştürmeleri Q#
description: Standart kitaplıklarda ortak ve Kullanıcı tanımlı tür dönüştürme işlevleri hakkında bilgi edinin Q# .
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868533"
---
# <a name="type-conversions"></a><span data-ttu-id="059a0-103">Tür Dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="059a0-103">Type Conversions</span></span> #

<span data-ttu-id="059a0-104">Q#**türü kesin belirlenmiş** bir dildir.</span><span class="sxs-lookup"><span data-stu-id="059a0-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="059a0-105">Özellikle Q# ayrı türler arasında örtük olarak atama yapmaz.</span><span class="sxs-lookup"><span data-stu-id="059a0-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="059a0-106">Örneğin, `1 + 2.0` geçerli bir Q# ifade değil.</span><span class="sxs-lookup"><span data-stu-id="059a0-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="059a0-107">Bunun yerine, Q# belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="059a0-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="059a0-108">Örneğin, bir <xref:microsoft.quantum.core.length> çıkış türüne sahiptir `Int` , bu nedenle çıktısının bir `Double` kayan nokta ifadesinin parçası olarak kullanılabilmesi için önce bir öğesine dönüştürülmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="059a0-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="059a0-109">Bu, işlevi kullanılarak yapılabilir <xref:microsoft.quantum.convert.intasdouble> :</span><span class="sxs-lookup"><span data-stu-id="059a0-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="059a0-110"><xref:microsoft.quantum.convert>Ad alanı,,,, ve gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar `Int` `Double` `BigInt` `Result` `Bool` :</span><span class="sxs-lookup"><span data-stu-id="059a0-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="059a0-111"><xref:microsoft.quantum.convert>Ad alanı, `FunctionAsOperation` işlevleri yeni işlemlere dönüştüren gibi bazı daha bazı Exotic dönüşümler de sağlar `'T -> 'U` `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="059a0-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="059a0-112">Son olarak, Q# standart kitaplık, ve gibi birçok kullanıcı tanımlı tür sağlar <xref:microsoft.quantum.math.complex> <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="059a0-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="059a0-113">Bu türlerle birlikte, standart kitaplık aşağıdaki gibi işlevler sağlar <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="059a0-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
