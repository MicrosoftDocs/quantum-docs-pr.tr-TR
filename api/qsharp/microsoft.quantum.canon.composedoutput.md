---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207471"
---
# <a name="composedoutput-function"></a>ComposedOutput işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`inner`Belirli bir girdi için ve öğesinin kompozisyonunun çıkışını döndürür `outer` .

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Giriş

### <a name="outer--u---v"></a>Dış: ' U-> ' V




### <a name="inner--t---u"></a>iç: 'T-> ' U




### <a name="target--t"></a>Hedef: 'T





## <a name="output--v"></a>Çıkış: ' V



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U


### <a name="v"></a>' V

