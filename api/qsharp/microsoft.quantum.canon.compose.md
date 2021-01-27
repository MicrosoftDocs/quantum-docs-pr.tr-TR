---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840901"
---
# <a name="compose-function"></a>Compose işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İki işlevin birleşimini döndürür.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Description

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