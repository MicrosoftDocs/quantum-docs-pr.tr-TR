---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: 3ea4757f6aa5125418b1e81db9f32e7b668eb359
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228704"
---
# <a name="mixedstatepreparationrequirements-user-defined-type"></a>MixedStatePreparationRequirements Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir karma durumu hazırlamak için gereken qubits sayısını temsil eder.

```qsharp

newtype MixedStatePreparationRequirements = (NTotalQubits : Int, (NIndexQubits : Int, NGarbageQubits : Int));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="ntotalqubits--int"></a>NTotalQubits: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="nindexqubits--int"></a>Nındexqubits: [Int](xref:microsoft.quantum.lang-ref.int)


### <a name="ngarbagequbits--int"></a>NGarbageQubits: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. PurifiedMixedState](xref:Microsoft.Quantum.PurifiedMixedState)