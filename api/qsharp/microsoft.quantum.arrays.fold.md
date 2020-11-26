---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221173"
---
# <a name="fold-function"></a>Fold işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlevi bir `f` dizi aracılığıyla yineler `array` , döndürür `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Giriş

### <a name="folder--statet---state"></a>klasör: (' durum, 'T)-> ' durumu

Dizi üzerinde katlanmak için bir işlev.


### <a name="state--state"></a>durum: ' durum

Klasörün başlangıç durumu.


### <a name="array--t"></a>dizi: 'T []

Üzerine katlanır değer dizisi.



## <a name="output--state"></a>Çıkış: ' durum

Tüm öğelerinin üzerinde yinelendikten sonra klasör tarafından döndürülen son durum `array` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="state"></a>' Durum

`folder`İşlevin üzerinde çalıştığı durumların türü, yani ilk bağımsız değişkeni olarak kabul eder ve döndürür.
### <a name="t"></a>Görüntülenemeyen

`array`Öğelerin türü.