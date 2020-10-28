---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728597"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="d9d36-102">LogicalANDMeasAndFix işlemi</span><span class="sxs-lookup"><span data-stu-id="d9d36-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="d9d36-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9d36-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9d36-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9d36-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9d36-105">Birden çok qubits 'in mantıksal ve ' lerini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="d9d36-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="d9d36-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d9d36-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="d9d36-107">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="d9d36-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="d9d36-108">Birden çok giriş ve ağ geçidi için qubits girişi.</span><span class="sxs-lookup"><span data-stu-id="d9d36-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="d9d36-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d9d36-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d9d36-110">VE çıktısının yazıldığı qubit.</span><span class="sxs-lookup"><span data-stu-id="d9d36-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="d9d36-111">Bu durumun her zaman $ \ket $ durumunda başlaması varsayılır {0} .</span><span class="sxs-lookup"><span data-stu-id="d9d36-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d9d36-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9d36-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d9d36-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d9d36-113">Remarks</span></span>

<span data-ttu-id="d9d36-114">`ctrlRegister`Tam olarak $2 $ qubit 'e sahip olduğunda, bu işlem ile eşdeğerdir ancak $ \ket $ ve $ `CCNOT` {001} -e ^ {ı \ pi/2} $ üzerinde $ \ket $ {101} ve $ \ket $ üzerinde ^ {i \ pi/2} $ $e aşama ile olan aşama {011} .</span><span class="sxs-lookup"><span data-stu-id="d9d36-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="d9d36-115">Adjoint Ayrıca yalnızca özel durumlarda (başvuruları gör) özgün işlemin tersi olan ölçü ve düzeltme yaklaşımına sahiptir, ancak daha az T-Gates kullanır.</span><span class="sxs-lookup"><span data-stu-id="d9d36-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="d9d36-116">Referanslar</span><span class="sxs-lookup"><span data-stu-id="d9d36-116">References</span></span>

- [<span data-ttu-id="d9d36-117">*Craig Gidney* , 1709,06648</span><span class="sxs-lookup"><span data-stu-id="d9d36-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)