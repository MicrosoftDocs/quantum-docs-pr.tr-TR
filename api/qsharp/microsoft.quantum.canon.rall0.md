---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728471"
---
# <a name="rall0-operation"></a>RAll0 işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir aşama kaydırma işlemi gerçekleştirir.

$R = \boldone-(1-e ^ {i \ Phi}) \ket{0\cnoktalar 0} \bra{0\cnoktalar 0} $.

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="phase--double"></a>Aşama: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Ph{0\cnoktalara 0} \bra{0\cnoktalar 0} $ için $ \phi $ aşaması uygulandı.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Durumu $R $ ile döndürüldüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. RAll1](xref:Microsoft.Quantum.Canon.RAll1)