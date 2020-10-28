---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: OptimizedBEXY işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727733"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="9443f-102">OptimizedBEXY işlemi</span><span class="sxs-lookup"><span data-stu-id="9443f-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="9443f-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="9443f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="9443f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9443f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9443f-105">$ (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1} üzerinde Pauli dizesini uygulayan bir Unitary $U $... " \{ 0, 1 \} $ ve $p $ içinde $z bir dizin üzerinde bulunan qubits $0... p $ Z_0 $.</span><span class="sxs-lookup"><span data-stu-id="9443f-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="9443f-106">Yani, $ $ \begin{hizalaması} U\ket {z} \ ayraç {p} \ Tus{\ PSI} = \ket{z}\ket{p} (X ^ {z + 1} \_ Kopyala ^ {z} \_ p) z \_ {p-1}... Z_0 \ket{\psı} \end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="9443f-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9443f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="9443f-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="9443f-108">Paulibaz: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9443f-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9443f-109">Bu qubit, $ \ket $ durumunda olduğunda {0} $X $ uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9443f-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="9443f-110">$ \Ket $ durumunda olduğunda {1} , $Y $ uygulanır.</span><span class="sxs-lookup"><span data-stu-id="9443f-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="9443f-111">ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9443f-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="9443f-112">Bu kaydın $ \ket{p} $ durumu, $X $ veya $Y $ ' nin uygulandığı qubit ' i belirler.</span><span class="sxs-lookup"><span data-stu-id="9443f-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="9443f-113">targetRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9443f-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9443f-114">Pauli işleçlerinin uygulandığı qubits 'in kaydı.</span><span class="sxs-lookup"><span data-stu-id="9443f-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9443f-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9443f-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9443f-116">Referanslar</span><span class="sxs-lookup"><span data-stu-id="9443f-116">References</span></span>

- <span data-ttu-id="9443f-117">Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="9443f-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>