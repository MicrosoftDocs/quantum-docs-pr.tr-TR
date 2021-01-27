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
# <a name="optimizedbexy-operation"></a><span data-ttu-id="1f522-102">OptimizedBEXY işlemi</span><span class="sxs-lookup"><span data-stu-id="1f522-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="1f522-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1f522-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1f522-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1f522-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1f522-105">$ (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1} üzerinde Pauli dizesini uygulayan bir Unitary $U $... " \{ 0, 1 \} $ ve $p $ içinde $z bir dizin üzerinde bulunan qubits $0... p $ Z_0 $.</span><span class="sxs-lookup"><span data-stu-id="1f522-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="1f522-106">Yani, $ $ \begin{hizalaması} U\ket {z} \ ayraç {p} \ Tus{\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psı} \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="1f522-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1f522-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="1f522-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="1f522-108">Paulibaz: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1f522-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1f522-109">Bu qubit, $ \ket $ durumunda olduğunda {0} $X $ uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1f522-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="1f522-110">$ \Ket $ durumunda olduğunda {1} , $Y $ uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1f522-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="1f522-111">ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1f522-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1f522-112">Bu kaydın $ \ket{p} $ durumu, $X $ veya $Y $ ' nin uygulandığı qubit ' i belirler.</span><span class="sxs-lookup"><span data-stu-id="1f522-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="1f522-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f522-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f522-114">Pauli işleçlerinin uygulandığı qubits 'in kaydı.</span><span class="sxs-lookup"><span data-stu-id="1f522-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f522-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f522-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="1f522-116">Başvurular</span><span class="sxs-lookup"><span data-stu-id="1f522-116">References</span></span>

- <span data-ttu-id="1f522-117">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="1f522-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>