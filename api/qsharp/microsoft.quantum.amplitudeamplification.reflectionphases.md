---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Reflectionaşamalar Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731970"
---
# <a name="reflectionphases-user-defined-type"></a>Reflectionaşamalar Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Leyebilir [](https://nuget.org/packages/)


Genize göre kısmi yansıtımları dizisinin aşamaları.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Başlangıç durumu hakkında yansıma için bir aşamalar dizisi.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Hedef durumu hakkında yansıma için bir aşamalar dizisi.

## <a name="remarks"></a>Açıklamalar

Her iki dizi de aynı uzunlukta olmalıdır. Çoğu durumda, hedef durum hakkında başlangıç durumu ve son aşama hakkında ilk aşamanın genel bir aşama kaydırma ve $0 $ olarak ayarlanması gerektiğini unutmayın.