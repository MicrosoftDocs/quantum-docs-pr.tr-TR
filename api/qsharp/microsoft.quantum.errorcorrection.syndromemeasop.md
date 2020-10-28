---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726965"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="ed337-102">SyndromeMeasOp Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="ed337-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="ed337-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ed337-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ed337-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed337-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed337-105">Hata düzeltme kod bloğunun eşitleniyor işlemini ölçmek için kullanılan bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="ed337-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="ed337-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ed337-106">Remarks</span></span>

<span data-ttu-id="ed337-107">İmza, `(LogicalRegister => Syndrome)` içindeki qubit ve bazı yardımcı qugeler üzerinde birlikte ortaklaşa çalışan bir işlemi temsil eder `LogicalRegister` ve ardından `Syndrome` Bu ölçümlerin sayısını temsil eden bir değer çıkarmak için yardımcı qubits ölçülerinin bir ölçümünü izler `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="ed337-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed337-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ed337-108">See Also</span></span>

- [<span data-ttu-id="ed337-109">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="ed337-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="ed337-110">Microsoft. hisse. Errordüzeltmesini. Syndrome</span><span class="sxs-lookup"><span data-stu-id="ed337-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)