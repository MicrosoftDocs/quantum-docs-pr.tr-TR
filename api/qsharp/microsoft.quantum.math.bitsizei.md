---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732759"
---
# <a name="bitsizei-function"></a>BitSizeI işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Negatif olmayan bir tamsayı için `a` , temsil etmesi gereken bitlerin sayısını döndürür `a` .

Diğer bir deyişle, $a < 2 ^ n $ gibi en küçük $n $ döndürür.

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Bit boyutu hesaplanacağı tamsayı.



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Bit boyutu `a` .