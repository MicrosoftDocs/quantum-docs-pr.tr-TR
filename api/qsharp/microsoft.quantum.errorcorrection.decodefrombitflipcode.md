---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Ayrışdefrombitflipcode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b16e84340053b6c1eab7b91ed8db0461b9eac98e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827555"
---
# <a name="decodefrombitflipcode-operation"></a>Ayrışdefrombitflipcode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme kodunun kodunu çözer.

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Giriş

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Bit çevirme kodunun kod bloğu.



## <a name="output--qubitqubit"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Mantıksal yazmaç içinde kodlanan verilerin bir kayıt düzeni ve Syndrome 'yi temsil etmek için kullanılan yardımcı qubits.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. hisse. Errordüzeltmesini. Encodeıntobitflipcode](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)