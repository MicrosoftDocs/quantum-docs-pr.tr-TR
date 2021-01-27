---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Addı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: a17403652cc2b2712defe52112a3ac599330da9f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843841"
---
# <a name="addi-operation"></a>Addı işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Kayıt boyutuna bağlı olarak, birlikte taşıma ve olmadan ekleme arasında otomatik olarak seçer `ys` .

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit adres.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

En az $n $ qubits ile ADDEND. Sonucu alacak.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

