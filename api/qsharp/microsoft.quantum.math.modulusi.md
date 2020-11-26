---
uid: Microsoft.Quantum.Math.ModulusI
title: ModulusI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusI
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6bbb3877b93e1fc6b38f85a716ba617311c7cfba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227786"
---
# <a name="modulusi-function"></a>ModulusI işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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