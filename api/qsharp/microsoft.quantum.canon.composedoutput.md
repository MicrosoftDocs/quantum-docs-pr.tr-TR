---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728837"
---
# <a name="composedoutput-function"></a>ComposedOutput işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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

