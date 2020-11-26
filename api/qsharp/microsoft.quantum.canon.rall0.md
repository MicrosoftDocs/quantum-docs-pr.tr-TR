---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205669"
---
# <a name="rall0-operation"></a>RAll0 işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir aşama kaydırma işlemi gerçekleştirir.

$R = \boldone-(1-e ^ {i \ Phi}) \ket{0\cnoktalar 0} \bra{0\cnoktalar 0} $.

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="phase--double"></a>Aşama: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Ph{0\cnoktalara 0} \bra{0\cnoktalar 0} $ için $ \phi $ aşaması uygulandı.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Durumu $R $ ile döndürüldüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. RAll1](xref:Microsoft.Quantum.Canon.RAll1)