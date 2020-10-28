---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 3f698a00b2c8d94b7cb3cca4f1721c659918f4a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732698"
---
# <a name="modulusi-function"></a>ModulusI işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .

```qsharp
function ModulusI (value : Int, modulus : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Kalan değerin hesaplandığı değer


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Resdues 'nin aldığı mod pozitif olmalıdır



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r

## <a name="remarks"></a>Açıklamalar

Bu işlev, işlecin `%` C# ' de nasıl davrandığı ile farklı davranır ve sonuçta `modulus - 1` , değer negatif olsa bile 0 ile her zaman pozitif bir tamsayı olur.