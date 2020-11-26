---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Issıralanmış işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220847"
---
# <a name="issorted-function"></a>Issıralanmış işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dizi verildiğinde, bu dizinin belirli bir karşılaştırma işlevi tarafından tanımlandığı şekilde sıralanıp sıralanmadığını döndürür.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Giriş

### <a name="comparison--tt---bool"></a>Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)

İki öğeyi karşılaştıran bir işlev `a` , daha küçük veya eşittir olarak kabul edilir `b` `comparison(a, b)` `true` .


### <a name="array--t"></a>dizi: 'T []

Denetlenecek dizi.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` ve yalnızca her öğe çifti için `a` ve `b` `array` Bu sırada oluşumda varsa, `comparison(a, b)` `true` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her öğesinin türü `array` .

## <a name="remarks"></a>Açıklamalar

İşlevin `comparison` geçişli olduğu varsayılır, `comparison(a, b)` ve `comparison(b, c)` daha sonra `comparison(a, c)` varsayılır. Bu özellik tutmadıysanız, bu işlevin çıktısı yanlış olabilir.