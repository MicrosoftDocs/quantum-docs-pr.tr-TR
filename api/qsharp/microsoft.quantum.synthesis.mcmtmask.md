---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734074"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


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

