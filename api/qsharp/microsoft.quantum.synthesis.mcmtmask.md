---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203034"
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

