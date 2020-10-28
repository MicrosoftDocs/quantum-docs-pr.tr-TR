---
uid: Microsoft.Quantum.Measurement.MResetZ
title: MResetZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetZ
qsharp.summary: Measures a single qubit in the Z basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 9f084b03504deea9fcf25e4c797c4bde3c97a995
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726509"
---
# <a name="mresetz-operation"></a>MResetZ işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Leyebilir [](https://nuget.org/packages/)


Z tabanında tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.

```qsharp
operation MResetZ (target : Qubit) : Result
```


## <a name="description"></a>Açıklama

$Z $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .

## <a name="input"></a>Giriş

### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ölçülecek tek bir qubit.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`target`Pauli $Z $ tabanında ölçüm sonucu.