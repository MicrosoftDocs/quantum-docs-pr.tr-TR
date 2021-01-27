---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Çoğullysi işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843006"
---
# <a name="multiplysi-operation"></a>Çoğullysi işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


İmzalanan tamsayıyı `xs` işaretli tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--signedlittleendian"></a>xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n bit çoğullıve (Signedlitttaendian)


### <a name="ys--signedlittleendian"></a>YS: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

n bit çarpanı (Signedlitttaendian)


### <a name="result--signedlittleendian"></a>Sonuç: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)

2N bit sonucu (Signedlitttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

