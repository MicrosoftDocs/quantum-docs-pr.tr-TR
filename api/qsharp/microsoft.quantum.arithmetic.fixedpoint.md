---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843197"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="de3f3-102">FixedPoint Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="de3f3-102">FixedPoint user defined type</span></span>

<span data-ttu-id="de3f3-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de3f3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de3f3-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="de3f3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="de3f3-105">Sabit noktalı bir sayıyı kodlayan bir qubits kaydını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="de3f3-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="de3f3-106">İkili noktanın solundaki qubit sayısına eşit bir tamsayı, yani 1 ' den büyük veya buna eşit ve bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="de3f3-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

