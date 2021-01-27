---
uid: Microsoft.Quantum.Arrays.Most
title: Çoğu işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845574"
---
# <a name="most-function"></a>Çoğu işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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