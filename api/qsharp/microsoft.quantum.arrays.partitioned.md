---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Bölümlenmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730087"
---
# <a name="partitioned-function"></a>Bölümlenmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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

