---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 28a7c7877a3d48fd5ba50384d7996017e7cdb14f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837259"
---
# <a name="optimizedbexy-operation"></a>OptimizedBEXY işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


$ (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1} üzerinde Pauli dizesini uygulayan bir Unitary $U $... " \{ 0, 1 \} $ ve $p $ içinde $z bir dizin üzerinde bulunan qubits $0... p $ Z_0 $. Yani, $ $ \begin{hizalaması} U\ket {z} \ ayraç {p} \ Tus{\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psı} \end{hizalaması} $ $

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="paulibasis--qubit"></a>Paulibaz: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bu qubit, $ \ket $ durumunda olduğunda {0} $X $ uygulanır. $ \Ket $ durumunda olduğunda {1} , $Y $ uygulanır.


### <a name="indexregister--littleendian"></a>ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Bu kaydın $ \ket{p} $ durumu, $X $ veya $Y $ ' nin uygulandığı qubit ' i belirler.


### <a name="targetregister--qubit"></a>targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Pauli işleçlerinin uygulandığı qubits 'in kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662