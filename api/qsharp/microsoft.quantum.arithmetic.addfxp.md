---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843867"
---
# <a name="addfxp-operation"></a>AddFxP işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Hisse Yazmaçları içinde depolanan iki sabit noktalı sayıyı ekler.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

$ \Ket{f_1} $ ve $ \ket{f_2} $ durumlarında sırasıyla iki sabit noktalı kayıt verildiğinde, $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ işlemini gerçekleştirir.

## <a name="input"></a>Giriş

### <a name="fp1--fixedpoint"></a>FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İlk sabit noktalı sayı


### <a name="fp2--fixedpoint"></a>FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

İkinci sabit noktalı sayı, iki girişin toplamını içerecek şekilde güncelleştirilecektir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Geçerli uygulama iki sabit noktalı sayının aynı nokta konumunun, en az önemli bitden ($n _i $ ve $p _i $ eşit olması gerekir.