---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852050"
---
# <a name="transformedoperation-function"></a>TransformedOperation işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlev ve bir işlem verildiğinde, girişi verilen işlev tarafından dönüştürülen yeni bir işlem döndürür.

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a>Giriş

### <a name="fn--u---t"></a>FN: ' U-> 'T

Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.


### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Dönüştürülecek işlem.



## <a name="output--u--unit"></a>Çıkış: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Yeni bir işlem olan tbat `fn` , girişiyle birlikte çağrı yapar ve sonuç çıktısını öğesine geçirir `op` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U



## <a name="example"></a>Örnek

Aşağıdaki çağrı, @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" giriş için tasarlanan bir işlemi @"Microsoft.Quantum.Arithmetic.BigEndian" , türü girdileri kabul eden bir işleme dönüştürmek için kullanır @"Microsoft.Quantum.Arithmetic.LittleEndian" :

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. TransformedOperationA](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [Microsoft. hisse. Canon. TransformedOperationC](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [Microsoft. hisse. Canon. TransformedOperationCA](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [Microsoft. hisse. Canon. Applywithınputtransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. hisse. Canon. oluşturulan](xref:Microsoft.Quantum.Canon.Composed)