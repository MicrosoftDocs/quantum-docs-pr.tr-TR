---
uid: Microsoft.Quantum.Arrays.Swapped
title: Takas edilen işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850945"
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

