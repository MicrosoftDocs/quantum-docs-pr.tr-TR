---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 2b38be5c196d81635daa8b478f6e727fdf378c62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850231"
---
# <a name="selectz-operation"></a>SelectZ işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Pauli $Z $ geçidini, $ \ket{p} $ Dizin durumunda bir qubits $p $ koşullu üzerinde uygulayan Unitary $U $. Yani, $ $ \begin{hizalaması} U\ket {p} \ ayraç {\ PSI} = \ket{p}Z \_ p\tus{\ PSI} \end{hizalaması} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="indexregister--littleendian"></a>ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bu kaydın $ \ket{p} $ durumu, $Z $ öğesinin uygulandığı qubit 'i belirler.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pauli işleçlerinin uygulandığı qubits 'in kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

