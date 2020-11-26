---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200263"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="1703b-102">SyndromeMeasOp Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="1703b-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="1703b-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1703b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1703b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1703b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1703b-105">Hata düzeltme kod bloğunun eşitleniyor işlemini ölçmek için kullanılan bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1703b-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="1703b-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1703b-106">Remarks</span></span>

<span data-ttu-id="1703b-107">İmza, `(LogicalRegister => Syndrome)` içindeki qubit ve bazı yardımcı qugeler üzerinde birlikte ortaklaşa çalışan bir işlemi temsil eder `LogicalRegister` ve ardından `Syndrome` Bu ölçümlerin sayısını temsil eden bir değer çıkarmak için yardımcı qubits ölçülerinin bir ölçümünü izler `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="1703b-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="1703b-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1703b-108">See Also</span></span>

- [<span data-ttu-id="1703b-109">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="1703b-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="1703b-110">Microsoft. hisse. Errordüzeltmesini. Syndrome</span><span class="sxs-lookup"><span data-stu-id="1703b-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)