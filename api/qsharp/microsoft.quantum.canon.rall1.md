---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728466"
---
# <a name="rall1-operation"></a>RAll1 işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir aşama kaydırma işlemi gerçekleştirir.

$R = \boldone-(1-e ^ {i \ Phi}) \ket{1\cnoktalar 1} \bra{1\cnoktalar 1} $.

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="phase--double"></a>Aşama: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Ph{1\cnoktalar 1} \bra{1\cnoktalar 1} $ için $ \phi $ aşaması uygulandı.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Durumu $R $ ile döndürüldüğü kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

