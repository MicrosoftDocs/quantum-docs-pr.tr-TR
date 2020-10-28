---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: e7e692059051fde295634c37892ec54e2cf1b095
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733847"
---
# <a name="modulusl-function"></a>ModulusL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


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