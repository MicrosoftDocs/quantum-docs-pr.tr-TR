---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730306"
---
# <a name="enumerated-function"></a>Numaralandırılmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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