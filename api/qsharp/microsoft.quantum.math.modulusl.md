---
uid: Microsoft.Quantum.Math.ModulusL
title: ModulusL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModulusL
qsharp.summary: Computes the canonical residue of `value` modulo `modulus`.
ms.openlocfilehash: 6be2edb052cf55f8e8465c76b5dcadeb61ff11ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842738"
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

Bu işlev, işlecin `%` C# ' de nasıl davrandığı ve sonuç olarak 0 ile arasında negatif olmayan bir tamsayı ve `modulus - 1` değer negatif olsa bile