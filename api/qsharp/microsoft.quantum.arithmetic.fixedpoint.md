---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223111"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Sabit noktalı bir sayıyı kodlayan bir qubits kaydını temsil eder. İkili noktanın solundaki qubit sayısına eşit bir tamsayı, yani 1 ' den büyük veya buna eşit ve bir hisse kayıt.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

