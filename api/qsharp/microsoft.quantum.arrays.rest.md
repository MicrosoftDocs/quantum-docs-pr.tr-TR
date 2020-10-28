---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730047"
---
# <a name="rest-function"></a>Rest işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


İlk dizi öğesinin bırakılmasının dışında, bir giriş dizisine eşit olan bir dizi oluşturur.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T []

İkinci-son öğelerine sahip bir dizi çıktı dizisini biçimlendirmek içindir.



## <a name="output--t"></a>Çıkış: 'T []

Öğeleri içeren bir dizi `array[1..Length(array) - 1]` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizi öğelerinin türü.