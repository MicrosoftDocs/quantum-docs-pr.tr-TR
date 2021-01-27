---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: Prepareıdentity işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: ec7e813110ccd9e6d499fc469fa27249a182b870
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855884"
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