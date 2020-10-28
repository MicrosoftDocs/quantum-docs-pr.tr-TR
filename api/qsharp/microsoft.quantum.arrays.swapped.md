---
uid: Microsoft.Quantum.Arrays.Swapped
title: Takas edilen işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729986"
---
# <a name="swapped-function"></a>Takas edilen işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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

