---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotationaşamalar Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731943"
---
# <a name="rotationphases-user-defined-type"></a>Rotationaşamalar Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Tek qubit döndürmeler dizisinin bir sırası için aşamalar yükseltme.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Açıklamalar

İlk parametre, tek qubit döndürmelerdeki bir ürün olarak ifade edilen, yansımalar için bir dizi aşamadan oluşur.
[ G.H. Düşük, ı. L. Chuang, https://arxiv.org/abs/1707.05391 ].