---
uid: Microsoft.Quantum.Canon.ApplyToPartitionA
title: ApplyToPartitionA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: f8f773e9fc3c18467185f9717a235649be8b385a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841300"
---
# <a name="applytopartitiona-operation"></a><span data-ttu-id="0790d-102">ApplyToPartitionA işlemi</span><span class="sxs-lookup"><span data-stu-id="0790d-102">ApplyToPartitionA operation</span></span>

<span data-ttu-id="0790d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0790d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0790d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0790d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0790d-105">Bir kaydın belirli bir bölümüne iki bölümden bir işlem çifti uygular.</span><span class="sxs-lookup"><span data-stu-id="0790d-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="0790d-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="0790d-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToPartitionA (op : ((Qubit[], Qubit[]) => Unit is Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0790d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="0790d-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj"></a><span data-ttu-id="0790d-108">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="0790d-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0790d-109">Verilen bölüme uygulanacak işlem çifti.</span><span class="sxs-lookup"><span data-stu-id="0790d-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="0790d-110">numberOfQubitsToFirstArgument: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0790d-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0790d-111">Hedeften itibaren bölümün ilk kısmına yerleştirilecek qubits sayısı.</span><span class="sxs-lookup"><span data-stu-id="0790d-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="0790d-112">Kalan qubits, bölümün ikinci bölümünü oluşturur.</span><span class="sxs-lookup"><span data-stu-id="0790d-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="0790d-113">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0790d-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0790d-114">Bölümlenen ve belirtilen iki işlem tarafından çalıştırılan bir qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="0790d-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0790d-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0790d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0790d-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0790d-116">See Also</span></span>

- [<span data-ttu-id="0790d-117">Microsoft. hisse. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="0790d-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)