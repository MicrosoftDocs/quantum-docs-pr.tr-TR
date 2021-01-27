---
uid: Microsoft.Quantum.Arrays.Reversed
title: Ters çevrilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845468"
---
# <a name="reversed-function"></a>Ters çevrilmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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