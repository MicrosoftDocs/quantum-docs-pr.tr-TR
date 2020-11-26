---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 36c6f227135b5ccaf1146fd7afdc8205d416c5dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227038"
---
# <a name="mresety-operation"></a>MResetY işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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