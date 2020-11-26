---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227089"
---
# <a name="measureallz-operation"></a>MeasureAllZ işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Çiçek bir qubitlerin bir kaydını Pauli Z temelinde ölçer.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Açıklama

Tüm kaydın eşlik düzeyini temsil eden $Z \otimes Z \otimes \cnoktalar \otimes Z $ temelinde bir qubit kaydı ölçer.

## <a name="input"></a>Giriş

### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ölçülecek kayıt.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

$Z \otimes Z \otimes \ cnoktalar \otimes Z $ ölçmesi sonucu.