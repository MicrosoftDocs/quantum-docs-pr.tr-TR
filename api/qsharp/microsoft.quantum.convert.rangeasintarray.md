---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850093"
---
# <a name="rangeasintarray-function"></a>RangeAsIntArray işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`arr`Start tarafından numaralandırılan tamsayılar dizisini oluşturur. adım.. erer.

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a>Giriş

### <a name="range--range"></a>Aralık: [Aralık](xref:microsoft.quantum.lang-ref.range)

Bir `Range` `start..step..end` diziye dönüştürülecek değerler.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

Tarafından tekrarlandırılmış değerlere karşılık gelen yeni tamsayılar dizisi `range` .

## <a name="example"></a>Örnek

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```