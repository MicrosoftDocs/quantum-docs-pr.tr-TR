---
uid: Microsoft.Quantum.Arithmetic.SquareSI
title: SquareSI işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareSI
qsharp.summary: Square signed integer `xs` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7fe4d27b974a06b019a2b15710fbc51b598027b4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221836"
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