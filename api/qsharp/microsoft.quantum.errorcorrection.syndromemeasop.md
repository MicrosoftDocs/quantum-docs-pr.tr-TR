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
# <a name="syndromemeasop-user-defined-type"></a>SyndromeMeasOp Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hata düzeltme kod bloğunun eşitleniyor işlemini ölçmek için kullanılan bir işlemi temsil eder.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a>Açıklamalar

İmza, `(LogicalRegister => Syndrome)` içindeki qubit ve bazı yardımcı qugeler üzerinde birlikte ortaklaşa çalışan bir işlemi temsil eder `LogicalRegister` ve ardından `Syndrome` Bu ölçümlerin sayısını temsil eden bir değer çıkarmak için yardımcı qubits ölçülerinin bir ölçümünü izler `Result[]` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. hisse. Errordüzeltmesini. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)