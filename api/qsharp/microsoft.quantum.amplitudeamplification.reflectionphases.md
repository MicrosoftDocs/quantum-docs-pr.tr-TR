---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Reflectionaşamalar Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847172"
---
# <a name="reflectionphases-user-defined-type"></a>Reflectionaşamalar Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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