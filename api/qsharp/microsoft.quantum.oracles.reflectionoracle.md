---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733338"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)

Leyebilir [](https://nuget.org/packages/)


Bir yansımayı bir Oracle temsil eder.

Bir yansıma Oracle, $O $, girdileri vardır:

- Yansıtılan alt alanın döndürüleceği $ \phi $ aşaması.
- Verilen yansımanın gerçekleştirileceği qubit kaydı.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL



## <a name="remarks"></a>Açıklamalar

Bu Oracle $O = \ cıvabitti-(1-e ^ {i \ Phi}) \ket{\psi}\bra{\psi} $, tek bir saf durum $ \ket{\psı} $ hakkında bir aşama $ \phi $ ile kısmi bir yansıma gerçekleştirir.