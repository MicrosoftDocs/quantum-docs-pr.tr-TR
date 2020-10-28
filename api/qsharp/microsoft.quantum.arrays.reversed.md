---
uid: Microsoft.Quantum.Arrays.Reversed
title: Ters çevrilmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730042"
---
# <a name="reversed-function"></a>Ters çevrilmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Giriş dizisi ile aynı öğeleri içeren, ancak ters sırada olan bir dizi oluşturun.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="array--t"></a>dizi: 'T []

Öğeleri ters sırada kopyalanacak olan bir dizi.



## <a name="output--t"></a>Çıkış: 'T []

Öğeleri içeren bir dizi `array[Length(array) - 1]` .. `array[0]`.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizi öğelerinin türü.