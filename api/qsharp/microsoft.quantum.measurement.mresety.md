---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 48aba7317d0e48d089ec6c4814efdee51bb8e2ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733794"
---
# <a name="mresety-operation"></a>MResetY işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Leyebilir [](https://nuget.org/packages/)


Y temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Açıklama

$Y $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .

## <a name="input"></a>Giriş

### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ölçülecek tek bir qubit.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`target`Pauli $Y $ tabanında ölçüm sonucu.