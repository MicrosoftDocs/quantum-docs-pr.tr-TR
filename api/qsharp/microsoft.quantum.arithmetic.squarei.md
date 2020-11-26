---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: Squareı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221870"
---
# <a name="squarei-operation"></a>Squareı işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


`xs` `result` , Başlangıçta sıfır olması gereken tamsayının karesini hesaplar.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit kare sayısı (Litttaendian)


### <a name="result--littleendian"></a>Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$2N $-bit sonucu (Litttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Kareyi hesaplamak için standart bir kaydırma ve ekleme yaklaşımı kullanır. , Düzenli bir çarpanı uygulamadan önce XS 'leri kopyalayan ve sonra kopyalama işlemini geri almadan önce XS 'i kopyalayan, düz iletme çözümüne kıyasla $n-$1 qubit tasarrufu sağlar.