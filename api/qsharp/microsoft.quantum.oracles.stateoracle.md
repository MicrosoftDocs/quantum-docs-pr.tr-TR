---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733346"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


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