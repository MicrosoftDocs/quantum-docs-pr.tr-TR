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
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="1b9c6-102">Kullanıcı tanımlı tür DecodeOp</span><span class="sxs-lookup"><span data-stu-id="1b9c6-102">DecodeOp user defined type</span></span>

<span data-ttu-id="1b9c6-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1b9c6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1b9c6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b9c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b9c6-105">Kodlanmış bir yazmacın bir fiziksel kayda ve bir Syndrome kaydetmek için kullanılan karalama qubits 'e kodunu çözen bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1b9c6-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="1b9c6-106">Bir DecodeOp 'ın bağımsız değişkeni, bir EncodeOp 'den dönüş ile aynıdır ve tam tersi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="1b9c6-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

