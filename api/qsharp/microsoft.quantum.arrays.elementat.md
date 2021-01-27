---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842814"
---
# <a name="elementat-function"></a>ElementAt işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizinin verilen dizininde öğesini döndürür.

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a>Giriş

### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)

Öğenin dizini


### <a name="array--t"></a>dizi: 'T []

Dizine eklenmekte olan dizi.



## <a name="output--t"></a>Çıkış: 'T



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="example"></a>Örnek

Üçüncü sayıyı dört faur tamsayı dizileri içinde alın. (0 dizininin sıranın _ilk_ değerine karşılık geldiğini unutmayın.)

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [Microsoft. hisse. Arrays. ElementsAt](xref:Microsoft.Quantum.Arrays.ElementsAt)