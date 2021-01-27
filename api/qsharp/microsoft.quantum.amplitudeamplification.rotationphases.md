---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: Rotationaşamalar Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843958"
---
# <a name="rotationphases-user-defined-type"></a>Rotationaşamalar Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek qubit döndürmeler dizisinin bir sırası için aşamalar yükseltme.

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a>Açıklamalar

İlk parametre, tek qubit döndürmelerdeki bir ürün olarak ifade edilen, yansımalar için bir dizi aşamadan oluşur.
[ G.H. Düşük, ı. L. Chuang, https://arxiv.org/abs/1707.05391 ].