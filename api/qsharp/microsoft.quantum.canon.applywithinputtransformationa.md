---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Applywithınputtransform Tiona işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841135"
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



## <a name="example"></a>Örnek

Aşağıdaki çağrı, @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" @"Microsoft.Quantum.Arithmetic.BigEndian" türünde bir girişe giriş için tasarlanan bir işlemi uygulamak için kullanır @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applywithınputtransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionc](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. hisse. Canon. Applywithınputtransform Tionca](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. hisse. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)