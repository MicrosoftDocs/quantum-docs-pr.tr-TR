---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726516"
---
# <a name="measureallz-operation"></a>MeasureAllZ işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Leyebilir [](https://nuget.org/packages/)


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