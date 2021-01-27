---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854483"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir yansımayı bir Oracle temsil eder.

Bir yansıma Oracle, $O $, girdileri vardır:

- Yansıtılan alt alanın döndürüleceği $ \phi $ aşaması.
- Verilen yansımanın gerçekleştirileceği qubit kaydı.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL



## <a name="remarks"></a>Açıklamalar

Bu Oracle $O = \ cıvabitti-(1-e ^ {i \ Phi}) \ket{\psi}\bra{\psi} $, tek bir saf durum $ \ket{\psı} $ hakkında bir aşama $ \phi $ ile kısmi bir yansıma gerçekleştirir.