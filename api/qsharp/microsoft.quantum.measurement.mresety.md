---
uid: Microsoft.Quantum.Measurement.MResetY
title: MResetY işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MResetY
qsharp.summary: Measures a single qubit in the Y basis, and resets it to a fixed initial state following the measurement.
ms.openlocfilehash: 2e41e76a46b68178a8a22b39131d6ca2a8c50b64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854647"
---
# <a name="mresety-operation"></a>MResetY işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Y temelinde tek bir qubit ölçer ve ölçüyü izleyen sabit bir başlangıç durumuna sıfırlar.

```qsharp
operation MResetY (target : Qubit) : Result
```


## <a name="description"></a>Description

$Y $-temelinde tek qubit ölçümü gerçekleştirir ve ölçü sonrasında qubitin $ \ket $ ' e döndürülmesini sağlar {0} .

## <a name="input"></a>Giriş

### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ölçülecek tek bir qubit.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`target`Pauli $Y $ tabanında ölçüm sonucu.