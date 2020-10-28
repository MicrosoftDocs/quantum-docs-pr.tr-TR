---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727050"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Y ekseni hakkında π/4 ile tek bir qubit döndürür.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
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