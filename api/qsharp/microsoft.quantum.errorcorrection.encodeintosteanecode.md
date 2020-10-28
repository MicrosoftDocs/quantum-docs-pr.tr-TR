---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: Encodeıntosteanecode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 39b8ab549413d9d5281f6b84a6e970c45242fca8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727080"
---
# <a name="encodeintosteanecode-operation"></a>Encodeıntosteanecode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


⟦ 7, 1, 3 ⟧ Steane hisse kodu altında kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen bir kodlama işlemi.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Giriş

### <a name="physregister--qubit"></a>physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Kodlanamayan bir hisse alma durumunu tutan bir qubit kaydı


### <a name="auxqubits--qubit"></a>Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bir kodlama işleminin gerçekleştirilebilmesi için başlangıçta sıfır ve hisse sisteme eklenen bir qubit kaydı.



## <a name="output--logicalregister"></a>Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Steane Kodlayıcısı uygulandıktan sonra durumu tutan bir hisse kaydı

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)