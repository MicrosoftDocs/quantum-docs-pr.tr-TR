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
# <a name="syndromemeasop-user-defined-type"></a>SyndromeMeasOp Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hata düzeltme kod bloğunun eşitleniyor işlemini ölçmek için kullanılan bir işlemi temsil eder.

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a>Örnek

$S = \langle ZZI, IZZ \rangle $, bir hataya dayanıklı olmayan bir şekilde sıfırdan fazla qubit kullanma:

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a>Açıklamalar

İmza, `(LogicalRegister => Syndrome)` içindeki qubit ve bazı yardımcı qugeler üzerinde birlikte ortaklaşa çalışan bir işlemi temsil eder `LogicalRegister` ve ardından `Syndrome` Bu ölçümlerin sayısını temsil eden bir değer çıkarmak için yardımcı qubits ölçülerinin bir ölçümünü izler `Result[]` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. hisse. Errordüzeltmesini. Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)