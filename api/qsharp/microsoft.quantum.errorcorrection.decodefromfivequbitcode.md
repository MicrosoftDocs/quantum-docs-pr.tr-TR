---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Ayrılan Defromfivequbitcode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 77c5614684f416c7d2e12914ec6246d3ef7098fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201113"
---
# <a name="decodefromfivequbitcode-operation"></a>Ayrılan Defromfivequbitcode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦ 5, 1, 3 ⟧ hisse kodu kodunu çözer.

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Giriş

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.



## <a name="output--qubitqubit"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. FiveQubitCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)