---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Encodeıntobitflipcode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727086"
---
# <a name="encodeintobitflipcode-operation"></a>Encodeıntobitflipcode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme koduna kodluyor.

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Giriş

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Korunacak verileri temsil eden fiziksel qubits kaydı.


### <a name="auxqubits--qubit"></a>Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Başlangıçta $ \ket {00} $ durumunda korunan verileri kodlamada kullanılacak bir yardımcı qubits kaydı.



## <a name="output--logicalregister"></a>Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Kodlama sırasında kullanılan fiziksel ve yardımcı qubit, mantıksal kayıt olarak gösterilir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)