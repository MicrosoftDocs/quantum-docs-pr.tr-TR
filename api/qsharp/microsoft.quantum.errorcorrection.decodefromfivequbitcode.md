---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Ayrılan Defromfivequbitcode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 9b4580cb88f03a16e3c9c55511d0ec5968cc636f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853164"
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