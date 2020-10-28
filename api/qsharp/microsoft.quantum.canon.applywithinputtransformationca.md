---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Applywithınputtransform Tionca işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c80ce0887a202a60de81c2d12fa95ce1eab59058
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728987"
---
# <a name="applywithinputtransformationca-operation"></a>Applywithınputtransform Tionca işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit
```


## <a name="input"></a>Giriş

### <a name="fn--u---t"></a>FN: ' U-> 'T

Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.


### <a name="op--t--unit-adj--ctl"></a>Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL

Uygulanacak işlem.


### <a name="input--u"></a>Giriş: ' U

İşleve bir giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applywithınputtransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. hisse. Canon. Applywithınputtransform Tiona](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionc](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. hisse. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)