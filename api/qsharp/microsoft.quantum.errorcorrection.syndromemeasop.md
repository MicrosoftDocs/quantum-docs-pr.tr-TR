---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850044"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="7aa8d-102">SyndromeMeasOp Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="7aa8d-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="7aa8d-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7aa8d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7aa8d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7aa8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7aa8d-105">Hata düzeltme kod bloğunun eşitleniyor işlemini ölçmek için kullanılan bir işlemi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="7aa8d-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="7aa8d-106">Example</span></span>

<span data-ttu-id="7aa8d-107">$S = \langle ZZI, IZZ \rangle $, bir hataya dayanıklı olmayan bir şekilde sıfırdan fazla qubit kullanma:</span><span class="sxs-lookup"><span data-stu-id="7aa8d-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="7aa8d-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7aa8d-108">Remarks</span></span>

<span data-ttu-id="7aa8d-109">İmza, `(LogicalRegister => Syndrome)` içindeki qubit ve bazı yardımcı qugeler üzerinde birlikte ortaklaşa çalışan bir işlemi temsil eder `LogicalRegister` ve ardından `Syndrome` Bu ölçümlerin sayısını temsil eden bir değer çıkarmak için yardımcı qubits ölçülerinin bir ölçümünü izler `Result[]` .</span><span class="sxs-lookup"><span data-stu-id="7aa8d-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="7aa8d-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7aa8d-110">See Also</span></span>

- [<span data-ttu-id="7aa8d-111">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="7aa8d-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="7aa8d-112">Microsoft. hisse. Errordüzeltmesini. Syndrome</span><span class="sxs-lookup"><span data-stu-id="7aa8d-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)