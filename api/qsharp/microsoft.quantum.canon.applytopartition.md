---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850550"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="ac11f-102">ApplyToPartition işlemi</span><span class="sxs-lookup"><span data-stu-id="ac11f-102">ApplyToPartition operation</span></span>

<span data-ttu-id="ac11f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac11f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac11f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac11f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac11f-105">Bir kaydın belirli bir bölümüne iki bölümden bir işlem çifti uygular.</span><span class="sxs-lookup"><span data-stu-id="ac11f-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ac11f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ac11f-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="ac11f-107">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac11f-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ac11f-108">Verilen bölüme uygulanacak işlem çifti.</span><span class="sxs-lookup"><span data-stu-id="ac11f-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="ac11f-109">numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ac11f-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ac11f-110">Hedeften itibaren bölümün ilk kısmına yerleştirilecek qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="ac11f-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="ac11f-111">Kalan qubits, bölümün ikinci bölümünü oluşturur.</span><span class="sxs-lookup"><span data-stu-id="ac11f-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ac11f-112">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ac11f-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ac11f-113">Bölümlenen ve belirtilen iki işlem tarafından çalıştırılan bir qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="ac11f-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac11f-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac11f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ac11f-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ac11f-115">See Also</span></span>

- [<span data-ttu-id="ac11f-116">Microsoft. hisse. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="ac11f-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="ac11f-117">Microsoft. hisse. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="ac11f-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="ac11f-118">Microsoft. hisse. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="ac11f-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)