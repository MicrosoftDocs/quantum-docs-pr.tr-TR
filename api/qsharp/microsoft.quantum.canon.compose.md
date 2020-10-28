---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728838"
---
# <a name="compose-function"></a>Compose işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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