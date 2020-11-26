---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224726"
---
# <a name="selectz-operation"></a><span data-ttu-id="4d030-102">SelectZ işlemi</span><span class="sxs-lookup"><span data-stu-id="4d030-102">SelectZ operation</span></span>

<span data-ttu-id="4d030-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4d030-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4d030-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4d030-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4d030-105">Pauli $Z $ geçidini, $ \ket{p} $ Dizin durumunda bir qubits $p $ koşullu üzerinde uygulayan Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="4d030-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="4d030-106">Yani, $ $ \begin{hizalaması} U\ket {p} \ ayraç {\ PSI} = \ket{p}Z \_ p\tus{\ PSI} \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="4d030-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4d030-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4d030-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="4d030-108">ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4d030-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4d030-109">Bu kaydın $ \ket{p} $ durumu, $Z $ öğesinin uygulandığı qubit 'i belirler.</span><span class="sxs-lookup"><span data-stu-id="4d030-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="4d030-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d030-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d030-111">Pauli işleçlerinin uygulandığı qubits 'in kaydı.</span><span class="sxs-lookup"><span data-stu-id="4d030-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d030-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d030-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

