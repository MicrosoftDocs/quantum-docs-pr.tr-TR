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
# <a name="type-conversions"></a><span data-ttu-id="2fb0d-103">Tür dönüştürmeleri</span><span class="sxs-lookup"><span data-stu-id="2fb0d-103">Type Conversions</span></span> #

<span data-ttu-id="2fb0d-104">S #, **türü kesin belirlenmiş** bir dildir.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="2fb0d-105">Özellikle, Q # ayrı türler arasında örtük olarak atama yapmaz.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="2fb0d-106">Örneğin, `1 + 2.0` geçerli bir Q # ifadesi değil.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="2fb0d-107">Bunun yerine, Q # belirli bir türün yeni değerlerini oluşturmak için çeşitli tür dönüştürme işlevleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="2fb0d-108">Örneğin, <xref:microsoft.quantum.core.length> bir `Int`çıkış türü vardır; bu nedenle, bir kayan nokta ifadesinin parçası olarak kullanılmadan önce çıktısının önce bir `Double` dönüştürmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="2fb0d-109">Bu işlem, <xref:microsoft.quantum.convert.intasdouble> işlevi kullanılarak yapılabilir:</span><span class="sxs-lookup"><span data-stu-id="2fb0d-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="2fb0d-110"><xref:microsoft.quantum.convert> ad alanı, `Int`, `Double`, `BigInt`, `Result`ve `Bool`gibi temel yerleşik türlerle çalışmak için ortak tür dönüştürme işlevleri sağlar:</span><span class="sxs-lookup"><span data-stu-id="2fb0d-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="2fb0d-111"><xref:microsoft.quantum.convert> ad alanı, işlevleri `'T -> 'U` yeni `'T => 'U`işlemlere dönüştüren `FunctionAsOperation`gibi bazı daha bazı Exotic dönüşümler de sağlar.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="2fb0d-112">Son olarak, Q # standart kitaplığı <xref:microsoft.quantum.math.complex> ve <xref:microsoft.quantum.arithmetic.littleendian>gibi bir dizi Kullanıcı tanımlı tür sağlar.</span><span class="sxs-lookup"><span data-stu-id="2fb0d-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="2fb0d-113">Bu türlerle birlikte, standart kitaplık <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>gibi işlevler sağlar:</span><span class="sxs-lookup"><span data-stu-id="2fb0d-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
