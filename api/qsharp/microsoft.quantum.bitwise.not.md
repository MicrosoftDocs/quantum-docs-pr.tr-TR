---
uid: Microsoft.Quantum.Bitwise.Not
title: Not işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842109"
---
# <a name="not-function"></a>Not işlevi

Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir tamsayı DEĞIL bit seviyesinde değer döndürür.
Bu, yerleşik işleçle aynı hesaplamayı gerçekleştirir `~~~` .

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="example"></a>Örnek

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a>Açıklamalar

Daha fazla ayrıntı için bkz. [C# ~ işleci](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) .