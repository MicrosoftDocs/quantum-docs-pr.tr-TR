---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840881"
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

