---
uid: Microsoft.Quantum.Arrays.Swapped
title: Takas edilen işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220136"
---
# <a name="swapped-function"></a>Takas edilen işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizide iki öğenin takas düzeyini uygular.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="firstindex--int"></a>Firstındex: [Int](xref:microsoft.quantum.lang-ref.int)

Takas edilecek ilk öğenin dizini.


### <a name="secondindex--int"></a>Ikincdizin: [Int](xref:microsoft.quantum.lang-ref.int)

Takas edilecek ikinci öğenin dizini.


### <a name="arr--t"></a>ARR: 'T []

Takas edilecek öğeler içeren dizi.



## <a name="output--t"></a>Çıkış: 'T []

Yerinde değiştirme uygulanmış dizi.

## <a name="example"></a>Örnek

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

