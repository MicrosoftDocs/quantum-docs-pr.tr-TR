---
uid: Microsoft.Quantum.Arrays.Excluding
title: İşlev hariç
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730287"
---
# <a name="excluding-function"></a>İşlev hariç

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="remove--int"></a>Remove: [Int](xref:microsoft.quantum.lang-ref.int)[]

Çıktının hangi öğelerin dışlanacağını belirten bir dizin dizisi.


### <a name="array--t"></a>dizi: 'T []

Çıkış dizisindeki değerlerin alındığı dizi.



## <a name="output--t"></a>Çıkış: 'T []

Bu gibi bir dizi, `output` `output[0]` dizininin içinde görünmeyen ilk öğe, örneğin, `array` Bu gibi `remove` `output[1]` ikinci öğe ve benzeri.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizi öğelerinin türü.