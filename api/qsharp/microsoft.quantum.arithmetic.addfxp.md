---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731903"
---
# <a name="addfxp-operation"></a>AddFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Hisse Yazmaçları içinde depolanan iki sabit noktalı sayıyı ekler.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Açıklama

$ \Ket{f_1} $ ve $ \ket{f_2} $ durumlarında sırasıyla iki sabit noktalı kayıt verildiğinde, $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ işlemini gerçekleştirir.

## <a name="input"></a>Giriş

### <a name="fp1--fixedpoint"></a>FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İlk sabit noktalı sayı


### <a name="fp2--fixedpoint"></a>FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İkinci sabit noktalı sayı, iki girişin toplamını içerecek şekilde güncelleştirilecektir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Geçerli uygulama iki sabit noktalı sayının aynı nokta konumunun, en az önemli bitden ($n _i $ ve $p _i $ eşit olması gerekir.