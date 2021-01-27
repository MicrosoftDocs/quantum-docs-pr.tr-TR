---
uid: Microsoft.Quantum.Preparation.MixedStatePreparationRequirements
title: MixedStatePreparationRequirements Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparationRequirements
qsharp.summary: Represents the number of qubits required in order to prepare a given mixed state.
ms.openlocfilehash: df57b7b43fc84f7ddf68392f6a2b7013225da730
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856942"
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