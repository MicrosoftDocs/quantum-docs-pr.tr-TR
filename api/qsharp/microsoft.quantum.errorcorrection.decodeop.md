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
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="708eb-102">Kullanıcı tanımlı tür DecodeOp</span><span class="sxs-lookup"><span data-stu-id="708eb-102">DecodeOp user defined type</span></span>

<span data-ttu-id="708eb-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="708eb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="708eb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="708eb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="708eb-105">Kodlanmış bir yazmacın bir fiziksel kayda ve bir Syndrome kaydetmek için kullanılan karalama qubits 'e kodunu çözen bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="708eb-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="708eb-106">Bir DecodeOp 'ın bağımsız değişkeni, bir EncodeOp 'den dönüş ile aynıdır ve tam tersi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="708eb-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

