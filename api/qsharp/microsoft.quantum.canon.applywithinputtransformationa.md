---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Applywithınputtransform Tiona işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207896"
---
# <a name="applywithinputtransformationa-operation"></a>Applywithınputtransform Tiona işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="fn--u---t"></a>FN: ' U-> 'T

Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.


### <a name="op--t--unit--is-adj"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Uygulanacak işlem.


### <a name="input--u"></a>Giriş: ' U

İşleve bir giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applywithınputtransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionc](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionca](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. hisse. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)