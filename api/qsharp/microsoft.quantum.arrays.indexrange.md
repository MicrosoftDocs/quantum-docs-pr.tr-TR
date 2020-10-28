---
uid: Microsoft.Quantum.Arrays.IndexRange
title: Indexrange işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730202"
---
# <a name="indexrange-function"></a>Indexrange işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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