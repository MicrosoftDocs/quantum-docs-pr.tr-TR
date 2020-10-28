---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Kullanıcı tanımlı tür DecodeOp
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727091"
---
# <a name="decodeop-user-defined-type"></a>Kullanıcı tanımlı tür DecodeOp

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Kodlanmış bir yazmacın bir fiziksel kayda ve bir Syndrome kaydetmek için kullanılan karalama qubits 'e kodunu çözen bir işlemi temsil eder.

Bir DecodeOp 'ın bağımsız değişkeni, bir EncodeOp 'den dönüş ile aynıdır ve tam tersi de geçerlidir.

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

