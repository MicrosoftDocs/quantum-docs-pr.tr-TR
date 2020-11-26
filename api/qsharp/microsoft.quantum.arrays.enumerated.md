---
uid: Microsoft.Quantum.Arrays.Enumerated
title: Numaralandırılmış işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221428"
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