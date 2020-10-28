---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731535"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="3a7a4-102">FixedPoint Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="3a7a4-102">FixedPoint user defined type</span></span>

<span data-ttu-id="3a7a4-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3a7a4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3a7a4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3a7a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3a7a4-105">Sabit noktalı bir sayıyı kodlayan bir qubits kaydını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3a7a4-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="3a7a4-106">İkili noktanın solundaki qubit sayısına eşit bir tamsayı, yani 1 ' den büyük veya buna eşit ve bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="3a7a4-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

