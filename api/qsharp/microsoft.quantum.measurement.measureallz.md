---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854680"
---
# <a name="measureallz-operation"></a>MeasureAllZ işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Çiçek bir qubitlerin bir kaydını Pauli Z temelinde ölçer.

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a>Description

Tüm kaydın eşlik düzeyini temsil eden $Z \otimes Z \otimes \cnoktalar \otimes Z $ temelinde bir qubit kaydı ölçer.

## <a name="input"></a>Giriş

### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ölçülecek kayıt.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

$Z \otimes Z \otimes \ cnoktalar \otimes Z $ ölçmesi sonucu.