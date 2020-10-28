---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727680"
---
# <a name="selectz-operation"></a>SelectZ işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Leyebilir [](https://nuget.org/packages/)


Pauli $Z $ geçidini, $ \ket{p} $ Dizin durumunda bir qubits $p $ koşullu üzerinde uygulayan Unitary $U $. Yani, $ $ \begin{hizalaması} U\ket {p} \ ayraç {\ PSI} = \ket{p}Z \_ p\tus{\ PSI} \end{hizalaması} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="indexregister--littleendian"></a>ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bu kaydın $ \ket{p} $ durumu, $Z $ öğesinin uygulandığı qubit 'i belirler.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pauli işleçlerinin uygulandığı qubits 'in kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

