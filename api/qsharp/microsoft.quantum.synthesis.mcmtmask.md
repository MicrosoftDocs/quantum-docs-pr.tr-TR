---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855371"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Birden çok kontrollü birden çok hedef Toffoli geçidini temsil eden bir tür.

İlk tamsayı, denetim hatları için bir bit maskesidir.  Ayarlanan bit dizinleri denetim satırı dizinlerine karşılık gelir.

İkinci tamsayı, hedef satırlar için bir bit maskesidir.  Ayarlanan bit dizinleri hedef satırı dizinlerine karşılık gelir.

Her iki tamsayının bit dizinlerinin ayrık olması gerekir.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="controlmask--int"></a>ControlMask: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [Int](xref:microsoft.quantum.lang-ref.int)

