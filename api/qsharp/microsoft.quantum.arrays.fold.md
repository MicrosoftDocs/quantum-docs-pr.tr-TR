---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848597"
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

## <a name="example"></a>Örnek

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```