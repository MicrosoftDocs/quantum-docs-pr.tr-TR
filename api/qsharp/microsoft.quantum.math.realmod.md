---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848358"
---
# <a name="realmod-function"></a>RealMod işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Örnek

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a>Açıklamalar

Bu işlev, birim çemberi gerçek satırı kaydırarak gerçek mod 'u hesaplar ve ardından girişe karşılık gelen birim çemberde açısını buluyor.
`minValue`Daha sonra giriş, birim çemberin nerede kesilip kesilbir şekilde belirtir.