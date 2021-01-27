---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Biriki katlanmış işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846240"
---
# <a name="cumulativefolded-function"></a>Biriki katlanmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Eşlenmiş ve katlama işlevini tek bir işlevle birleştirir

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Description

Bu işlev, `fn` bir başlangıç durumundan başlayarak işlevi dizi üzerinden yineler `state` ve ilk durumu dahil etmez tüm ara değerlerini döndürür.

## <a name="input"></a>Giriş

### <a name="fn--statet---state"></a>FN: (' durum, 'T)-> ' durumu

Dizi üzerinde katlanmak için bir işlev


### <a name="state--state"></a>durum: ' durum

Katlanın ilk durumu


### <a name="array--t"></a>dizi: 'T []

Katlaneklenecek değer dizisi



## <a name="output--state"></a>Çıkış: ' State []

Son durum da dahil olmak üzere tüm ara durumlar, ilk durumu değil.
Çıktı dizisinin uzunluğu, ile aynı uzunluktadır `array` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="state"></a>' Durum

İşlevin üzerinde çalıştığı durumların türü, `fn` Yani, ilk giriş ve dönüş olarak kabul eder.
### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.

## <a name="example"></a>Örnek

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```