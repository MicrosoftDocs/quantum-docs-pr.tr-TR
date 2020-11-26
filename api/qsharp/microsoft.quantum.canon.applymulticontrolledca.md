---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209290"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="9c0c2-102">ApplyMultiControlledCA işlemi</span><span class="sxs-lookup"><span data-stu-id="9c0c2-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="9c0c2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9c0c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9c0c2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9c0c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9c0c2-105">Listedir denetimli bir işlemin çarpma denetimli bir sürümünü uygular.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="9c0c2-106">Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9c0c2-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="9c0c2-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit--is-adj"></a><span data-ttu-id="9c0c2-108">Singlycontroltadop: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfastı</span><span class="sxs-lookup"><span data-stu-id="9c0c2-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9c0c2-109">Tek bir qubit üzerinde denetlenen bir işlem.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="9c0c2-110">İşlemin bağımsız değişkenindeki ilk qubit bir denetim olarak kabul edilir ve REST 'in hedef qubit olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="9c0c2-111">`ApplyMultiControlled` her zaman `singlyControlledOp` en az 1 uzunluğunda bir bağımsız değişkenle çağırır.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="9c0c2-112">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="9c0c2-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="9c0c2-113">Oluşturma için kullanılacak kontrollü kontrollü olmayan ağ geçidi.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="9c0c2-114">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9c0c2-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9c0c2-115">`singlyControlledOp`Üzerinde kontrol edilecek qubits.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="9c0c2-116">Uzunluğu `controls` en az 1 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="9c0c2-117">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9c0c2-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9c0c2-118">Üzerinde davranan hedef qubit `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="9c0c2-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9c0c2-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9c0c2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9c0c2-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9c0c2-120">Remarks</span></span>

<span data-ttu-id="9c0c2-121">Bu işlem yalnızca temiz bir anyenla qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="9c0c2-122">Açıklama ve devre diyagramı için bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="9c0c2-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="9c0c2-123">Başvurular</span><span class="sxs-lookup"><span data-stu-id="9c0c2-123">References</span></span>

- [<span data-ttu-id="9c0c2-124">*Michael A. Nielsen, Isaac L. Chuang*, hisse hesaplaması ve hisse bilgisi</span><span class="sxs-lookup"><span data-stu-id="9c0c2-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="9c0c2-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9c0c2-125">See Also</span></span>

- [<span data-ttu-id="9c0c2-126">Microsoft. hisse. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="9c0c2-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)