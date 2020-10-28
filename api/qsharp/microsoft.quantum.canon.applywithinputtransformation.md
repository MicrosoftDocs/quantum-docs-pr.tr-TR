---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Applywithınputtransformation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728999"
---
# <a name="applywithinputtransformation-operation"></a>Applywithınputtransformation işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a>Giriş

### <a name="fn--u---t"></a>FN: ' U-> 'T

Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.


### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak işlem.


### <a name="input--u"></a>Giriş: ' U

İşleve bir giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applywithınputtransform Tiona](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionc](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionca](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. hisse. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)