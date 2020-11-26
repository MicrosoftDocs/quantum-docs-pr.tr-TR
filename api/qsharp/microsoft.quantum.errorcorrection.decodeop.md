---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Kullanıcı tanımlı tür DecodeOp
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: f1fc2851b7ed8b12cf8a47fabe794235a3083d31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201017"
---
# <a name="decodeop-user-defined-type"></a>Kullanıcı tanımlı tür DecodeOp

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kodlanmış bir yazmacın bir fiziksel kayda ve bir Syndrome kaydetmek için kullanılan karalama qubits 'e kodunu çözen bir işlemi temsil eder.

Bir DecodeOp 'ın bağımsız değişkeni, bir EncodeOp 'den dönüş ile aynıdır ve tam tersi de geçerlidir.

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

