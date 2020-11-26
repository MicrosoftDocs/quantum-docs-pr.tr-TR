---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200807"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Y ekseni hakkında π/4 ile tek bir qubit döndürür.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>Açıklama

Hakkında π/4 döndürme gerçekleştirir `Y` .

Döndürme, bir sihirli durum tüketerek gerçekleştirilir; diğer bir deyişle, $ $ \begin{hizalaması} \cos\frac{\pi} {8} {0} \tus+ \sin \ FRAC{\pi} {8} \tusöğesinin bir kopyasıdır {1} .
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="data--qubit"></a>veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)

$ \Pi/$4 ile $Y $ hakkında bir qubit döndürülür.


### <a name="magic--qubit"></a>Magic: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Başlangıçta Magic durumunda bir qubit. Bu işlemin aşağıdaki uygulaması `magic` $ \ket {0} $ durumuna döndürülür.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Aşağıdakiler eşdeğerdir:

```qsharp
Ry(PI() / 4.0, data);
```

ve

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Bu işlem, `Adjoint` functor 'ı destekler, bu durumda aynı sihirli durum tüketilen, ancak veri qubit üzerindeki etki bir $-\ Pi/4 $ $Y $-rotadır.