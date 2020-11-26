---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226613"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Durum hazırlığı için bir Oracle temsil eder.

Oracle $O $ girdileri şunlardır:

- Qubit $f $ bayrağını dizinleyen bir tamsayı.
- System Register $s $, istenen hisse durumu $ \ket{\psı} s $ ' i depolayacak \_ .

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Açıklamalar

Bu Oracle tarafından tanımlanan bu Oracle $ $ O\ket {0} \_ {f} \ayraç {0} \_ s = \lambda\tusf\ket {1} \_ {\ PSI} \_ s + \sqrt{1-| \lambda | ^ 2} \demet {0} \_ f\cnoktalar, $ $ $ {0} \_ {0} \_ \tusf $ tarafından işaretlenen esasına göre $ \ket{\psı} s $ hedef durumu $ \_ \lambda $, genlik $ \lambda $ oluşturmak için hesaplama {1} tabanlı durum $ \tus{f} \tuss $ üzerinde çalışır \_ .
İlk parametre, $ \ket f $ ' nin qubit kaydına yönelik bir dizindir {0} \_ . İkinci parametrenin her ikisi de kaydettirir.