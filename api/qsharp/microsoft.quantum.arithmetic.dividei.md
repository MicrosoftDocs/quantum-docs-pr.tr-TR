---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 4cff191e1f9d42659768b4059e477f1a07948ba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223315"
---
# <a name="dividei-operation"></a>DivideI işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


İki hisse tamsayının böler.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`xs` kalanı tutar `xs - floor(xs/ys) * ys` ve `result` tutacaktır `floor(xs/ys)` .

## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit bölünmeleri, kalanı ile değiştirilirler.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit bölen


### <a name="result--littleendian"></a>Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit sonucu, başlangıçta $ \ket $ durumunda olmalıdır {0} ve tamsayı bölümünün sonucuyla değiştirilmelidir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bölme uygulamak için standart bir kaydırma ve çıkarma yaklaşımı kullanır.
Denetlenen sürüm, çıkarma işlemi için ek denetimler gerekli değildir.