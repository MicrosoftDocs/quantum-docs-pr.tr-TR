---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859265"
---
# <a name="applyunitary-operation"></a>ApplyUnitary işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


2 ^ n x 2 ^ n Unitary matrisi tarafından tanımlanan geçit uygular.

Matris Unitary değilse veya boyut yanlış ise başarısız olur.

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="unitary--complex"></a>Unitary: [karmaşık](xref:Microsoft.Quantum.Math.Complex)[] []

2 ^ n x 2 ^ n Unitary, işlemi açıklayan matris.
Matris Unitary veya uygun boyutta değilse, bir özel durum oluşturur.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

İşlem-yazmaç uzunluğu için gereken qubitleri.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

