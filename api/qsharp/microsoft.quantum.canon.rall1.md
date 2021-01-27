---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: f4159a6cc0e0b4f18f418a53a309b5ce527b2608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852254"
---
# <a name="rall1-operation"></a>RAll1 işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir aşama kaydırma işlemi gerçekleştirir.

$R = \boldone-(1-e ^ {i \ Phi}) \ket{1\cnoktalar 1} \bra{1\cnoktalar 1} $.

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="phase--double"></a>Aşama: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Ph{1\cnoktalar 1} \bra{1\cnoktalar 1} $ için $ \phi $ aşaması uygulandı.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Durumu $R $ ile döndürüldüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

