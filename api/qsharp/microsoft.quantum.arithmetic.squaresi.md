---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 161b45766c6f4d500d25def24aa509ee7fdc8628
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842936"
---
# <a name="squaresi-operation"></a>SquareSI işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Kare işaretli tamsayı `xs` ve sonucu `result` , başlangıçta sıfır olması gereken içinde depolar.

```qsharp
operation SquareSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--signedlittleendian"></a>xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n bitlik tamsayı-kare (Signedlittliendian)


### <a name="result--signedlittleendian"></a>Sonuç: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

2N bit sonucu (Signedlitttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Uygulama, IntegerSquare kullanır.