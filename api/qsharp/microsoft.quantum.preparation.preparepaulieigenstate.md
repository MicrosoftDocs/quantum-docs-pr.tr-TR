---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: 473bb2fa4429a14f69bcae4573354aad87dc37df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854350"
---
# <a name="preparepaulieigenstate-operation"></a>PreparePauliEigenstate işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Verilen Pauli işlecinin pozitif eigenstate değeri için bir qubit hazırlar.
Identity işleci verilirse, qubit, yüksek ölçüde karışık duruma hazırlanır.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Description

Qubit başlangıçta $ \ket {0} $ durumundaysa, bu işlem belirli bir Pauli işlecinin $ + $1 eigenstate veya için `PauliI` (bkz.) yerine en düşük karma durumunda qubit 'i hazırlar (bkz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> .).

Qubit $ \ket $ dışında bir durumdaysa {0} , bu işlem şu kapıları uygular: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ for `PauliZ` and for <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .

## <a name="input"></a>Giriş

### <a name="basis--pauli"></a>temel: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli işleci $P $.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hazırlanmaya yönelik bir qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

$ \Ket{+} $ durumunda bir qubit hazırlamak için:

```qsharp
using (q = Qubit()) {
    PreparePauliEigenstate(PauliX, qubit);
    // ...
}
```