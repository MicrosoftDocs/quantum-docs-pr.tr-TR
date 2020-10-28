---
uid: Microsoft.Quantum.Arrays.Most
title: Çoğu işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730103"
---
# <a name="most-function"></a>Çoğu işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Son dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T []

İlk olarak ikinci-son öğeleri olan bir dizi çıktı dizisini biçimlendirmek içindir.



## <a name="output--t"></a>Çıkış: 'T []

Öğeleri içeren bir dizi `array[0..Length(array) - 2]` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizi öğelerinin türü.