---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Hazırlık eşitlenmiş bit işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732650"
---
# <a name="preparequbit-operation"></a>Hazırlık eşitlenmiş bit işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


`Zero`Verilen Pauli işlecinin ıdgenstate ' i () ile bir qubit hazırlar.
Identity işleci verilirse, qubit, yüksek ölçüde karışık duruma hazırlanır.

Qubit başlangıçta $ \ket {0} $ durumundaysa, bu işlem belirli bir Pauli işlecinin $ + $1 eigenstate veya için `PauliI` (bkz.) yerine en düşük karma durumunda qubit 'i hazırlar (bkz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> .).

Qubit $ \ket $ dışında bir durumdaysa {0} , bu işlem şu kapıları uygular: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` and for <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="basis--pauli"></a>temel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli işleci $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hazırlanmaya yönelik bir qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

