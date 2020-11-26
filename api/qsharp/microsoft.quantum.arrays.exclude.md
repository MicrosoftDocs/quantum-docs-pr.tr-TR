---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221360"
---
# <a name="exclude-function"></a>Exclude işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir dizin listesindeki öğeleri dışlayarak başka bir dizinin öğelerini içeren bir dizi döndürür.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
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