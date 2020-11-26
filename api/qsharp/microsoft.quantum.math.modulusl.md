---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 5c9a8ceceac5d2cdac6b82f7f74a85e9443382a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194942"
---
# <a name="modulusl-function"></a>ModulusL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Modülden kaynaklanan kurallı bir şekilde `value` hesaplar `modulus` .

```qsharp
function ModulusL (value : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Giriş

### <a name="value--bigint"></a>değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Kalan değerin hesaplandığı değer


### <a name="modulus--bigint"></a>mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Resdues 'nin aldığı mod pozitif olmalıdır



## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

0 ile 1 arasında $ ve `modulus - 1` `value - r` mod ile bölünebilen tamsayı $r

## <a name="remarks"></a>Açıklamalar

Bu işlev, işlecin `%` C# ' de nasıl davrandığı ile farklı davranır ve sonuçta `modulus - 1` , değer negatif olsa bile 0 ile her zaman pozitif bir tamsayı olur.