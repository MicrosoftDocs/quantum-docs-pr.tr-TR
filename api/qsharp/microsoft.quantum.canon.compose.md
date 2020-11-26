---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216770"
---
# <a name="compose-function"></a>Compose işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki işlevin birleşimini döndürür.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Açıklama

$ Ve $g $ $f iki işlev verildiğinde, $f \circ g $ temsil eden yeni bir işlev döndürür.

## <a name="input"></a>Giriş

### <a name="outer--u---v"></a>Dış: ' U-> ' V

Uygulanacak ikinci işlev.


### <a name="inner--t---u"></a>iç: 'T-> ' U

Uygulanacak ilk işlev.



## <a name="output--t---v"></a>Çıkış: 'T-> ' V

$, $F (g (x)) = h (x) $ $x tüm girişler için $h $ gibi yeni bir işlev.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak ilk işlevin giriş türü.
### <a name="u"></a>' U

Uygulanacak ilk işlevin çıkış türü ve uygulanacak ikinci işlevin giriş türü.
### <a name="v"></a>' V

Uygulanacak ikinci işlevin çıkış türü.