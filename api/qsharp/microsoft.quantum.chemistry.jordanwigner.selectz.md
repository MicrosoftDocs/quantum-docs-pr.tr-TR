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
# <a name="selectz-operation"></a><span data-ttu-id="76610-102">SelectZ işlemi</span><span class="sxs-lookup"><span data-stu-id="76610-102">SelectZ operation</span></span>

<span data-ttu-id="76610-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="76610-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="76610-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76610-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76610-105">Pauli $Z $ geçidini, $ \ket{p} $ Dizin durumunda bir qubits $p $ koşullu üzerinde uygulayan Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="76610-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="76610-106">Yani, $ $ \begin{hizalaması} U\ket {p} \ ayraç {\ PSI} = \ket{p}Z \_ p\tus{\ PSI} \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="76610-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="76610-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="76610-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="76610-108">ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="76610-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="76610-109">Bu kaydın $ \ket{p} $ durumu, $Z $ öğesinin uygulandığı qubit 'i belirler.</span><span class="sxs-lookup"><span data-stu-id="76610-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="76610-110">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="76610-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="76610-111">Pauli işleçlerinin uygulandığı qubits 'in kaydı.</span><span class="sxs-lookup"><span data-stu-id="76610-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76610-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76610-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

