---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848136"
---
# <a name="enumerated-function"></a>Numaralandırılmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizi verildiğinde, orijinal dizinin öğelerini içeren yeni bir dizi döndürür ve her bir öğenin indisleriyle birlikte.

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>Giriş

### <a name="array--telement"></a>dizi: ' TElement []

Öğeleri Numaralandırılacak olan bir dizi.



## <a name="output--inttelement"></a>Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ' TElement) []

Özgün dizinin öğelerini dizinleriyle birlikte içeren yeni bir dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="telement"></a>' TElement

Dizinin öğe türü.

## <a name="example"></a>Örnek

Aşağıdaki `for` döngüler eşdeğerdir:

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```