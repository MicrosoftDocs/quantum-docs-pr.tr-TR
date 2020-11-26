---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Encodeıntofivequbitcode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200994"
---
# <a name="encodeintofivequbitcode-operation"></a>Encodeıntofivequbitcode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦ 5, 1, 3 ⟧ hisse koduna kodluyor.

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Giriş

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Kodlanamayan bir durumu temsil eden bir qubit. Bu dizi `Qubit[]` 1 uzunluktadır.


### <a name="auxqubits--qubit"></a>Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Kodlanmış durumu temsil etmek için kullanılacak yardımcı qubit kaydı.



## <a name="output--logicalregister"></a>Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Kodlanmış durumu depolayan türdeki fiziksel qubit dizisi `LogicalRegister` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)