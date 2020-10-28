---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731039"
---
# <a name="realmod-function"></a>RealMod işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


İki gerçek sayı arasındaki mod sayısını hesaplar.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Giriş

### <a name="value--double"></a>değer: [Double](xref:microsoft.quantum.lang-ref.double)

' Nin mod ' A kadar olan gerçek bir sayı $x.


### <a name="modulo--double"></a>Modül: [Double](xref:microsoft.quantum.lang-ref.double)

$X $ ' in ' i ' ile karşılaştırıldığında, gerçek sayı.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Bu işlev tarafından döndürülecek en küçük değer.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Açıklamalar

Bu işlev, birim çemberi gerçek satırı kaydırarak gerçek mod 'u hesaplar ve ardından girişe karşılık gelen birim çemberde açısını buluyor.
`minValue`Daha sonra giriş, birim çemberin nerede kesilip kesilbir şekilde belirtir.