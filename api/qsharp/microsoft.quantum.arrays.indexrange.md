---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Indexrange işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220952"
---
# <a name="indexrange-function"></a>Indexrange işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir dizi verildiğinde, for döngüsünde kullanılmak üzere uygun olan, bu dizinin dizinlerinin üzerinde bir Aralık döndürür.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Giriş

### <a name="array--telement"></a>dizi: ' TElement []

Bir dizin aralığı döndürülmesi gereken dizi.



## <a name="output--range"></a>Çıkış: [Aralık](xref:microsoft.quantum.lang-ref.range)

Dizinin tüm dizinleri üzerinde bir Aralık.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="telement"></a>' TElement

Dizinin öğe türü.