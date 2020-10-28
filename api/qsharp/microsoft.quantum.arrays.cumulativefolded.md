---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Biriki katlanmış işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730367"
---
# <a name="cumulativefolded-function"></a>Biriki katlanmış işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


Eşlenmiş ve katlama işlevini tek bir işlevle birleştirir

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Açıklama

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