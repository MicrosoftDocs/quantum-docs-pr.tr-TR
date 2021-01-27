---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Bölümlenmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845552"
---
# <a name="partitioned-function"></a>Bölümlenmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir diziyi birden çok parçaya böler.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Giriş

### <a name="nelements--int"></a>nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]

Dizinin her bir parçasındaki öğe sayısı


### <a name="arr--t"></a>ARR: 'T []

Bölünecek giriş dizisi.



## <a name="output--t"></a>Çıkış: 'T [] []

İlk dizinin birinci ilk `nElements[0]` `arr` ve ikinci dizi ise ve ' nin bir sonraki ' dır `nElements[1]` `arr` . Son dizi kalan tüm öğeleri içerir.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="example"></a>Örnek

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```