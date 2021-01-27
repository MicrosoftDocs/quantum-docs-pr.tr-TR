---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Çoğullyi işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 8615d0d5100c26f86264ceaecadb7783563216a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843038"
---
# <a name="multiplyi-operation"></a>Çoğullyi işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Tamsayıyı `xs` tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit çoğullıve (Litttaendian)


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit çarpanı (Littliendian)


### <a name="result--littleendian"></a>Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit sonucu (Litttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Çarpma uygulamak için standart bir kaydırma ve ekleme yaklaşımı kullanır.
Denetlenen sürüm, $x _i $ ' ı Control qubits üzerinde bir anment quge 'ya kopyalayarak ve sonra da anment qubit üzerinde ek bir şekilde denetlenerek geliştirilmiştir.