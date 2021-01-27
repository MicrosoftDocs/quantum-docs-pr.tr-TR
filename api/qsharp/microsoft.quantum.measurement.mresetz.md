---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: fc9ba6576b56d7df1a57334e1da46b9c48376ecb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853734"
---
# <a name="mresetz-operation"></a>MResetZ işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Z tabanında tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Description

$Z $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .

## <a name="input"></a>Giriş

### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ölçülecek tek bir qubit.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`target`Pauli $Z $ tabanında ölçüm sonucu.