---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195860"
---
# <a name="bitsizei-function"></a>BitSizeI işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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