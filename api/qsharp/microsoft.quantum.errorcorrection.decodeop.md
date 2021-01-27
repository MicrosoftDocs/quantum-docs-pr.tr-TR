---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: Kullanıcı tanımlı tür DecodeOp
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 2b3d4558f6528c2e0f597398d12fc9331ab381b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827368"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="b33ae-102">Kullanıcı tanımlı tür DecodeOp</span><span class="sxs-lookup"><span data-stu-id="b33ae-102">DecodeOp user defined type</span></span>

<span data-ttu-id="b33ae-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b33ae-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b33ae-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b33ae-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b33ae-105">Kodlanmış bir yazmacın bir fiziksel kayda ve bir Syndrome kaydetmek için kullanılan karalama qubits 'e kodunu çözen bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="b33ae-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="b33ae-106">Bir DecodeOp 'ın bağımsız değişkeni, bir EncodeOp 'den dönüş ile aynıdır ve tam tersi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="b33ae-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

