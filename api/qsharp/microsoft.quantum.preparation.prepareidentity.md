---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Prepareıdentity işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210446"
---
# <a name="prepareidentity-operation"></a>Prepareıdentity işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kayıt verildiğinde, bu kaydı, en yüksek düzeyde karışık durumda hazırlar.

Kayıt, her bir qubit 'e tüm depolarizing kanalını uygulayarak $ \ cıvadone/2 ^ N $ durumunda hazırlandı; burada $N $ kaydın uzunluğudur.

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Durumu yukarıda açıklanan şekilde depolarized olan bir kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. hazırlık Esingliqubitişdentity](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)