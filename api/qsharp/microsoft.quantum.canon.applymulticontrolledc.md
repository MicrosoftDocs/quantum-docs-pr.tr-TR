---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218419"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="91a66-102">ApplyMultiControlledC işlemi</span><span class="sxs-lookup"><span data-stu-id="91a66-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="91a66-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91a66-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91a66-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91a66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91a66-105">Listedir denetimli bir işlemin çarpma denetimli bir sürümünü uygular.</span><span class="sxs-lookup"><span data-stu-id="91a66-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="91a66-106">Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="91a66-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="91a66-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="91a66-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="91a66-108">Singlycontroltadop: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91a66-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="91a66-109">Tek bir qubit üzerinde denetlenen bir işlem.</span><span class="sxs-lookup"><span data-stu-id="91a66-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="91a66-110">İşlemin bağımsız değişkenindeki ilk qubit bir denetim olarak kabul edilir ve REST 'in hedef qubit olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="91a66-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="91a66-111">`ApplyMultiControlled` her zaman `singlyControlledOp` en az 1 uzunluğunda bir bağımsız değişkenle çağırır.</span><span class="sxs-lookup"><span data-stu-id="91a66-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="91a66-112">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="91a66-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="91a66-113">Oluşturma için kullanılacak kontrollü kontrollü olmayan ağ geçidi.</span><span class="sxs-lookup"><span data-stu-id="91a66-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="91a66-114">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="91a66-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="91a66-115">`singlyControlledOp`Üzerinde kontrol edilecek qubits.</span><span class="sxs-lookup"><span data-stu-id="91a66-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="91a66-116">Uzunluğu `controls` en az 1 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="91a66-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="91a66-117">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="91a66-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="91a66-118">Üzerinde davranan hedef qubit `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="91a66-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91a66-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91a66-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="91a66-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="91a66-120">Remarks</span></span>

<span data-ttu-id="91a66-121">Bu işlem yalnızca temiz bir anyenla qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="91a66-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="91a66-122">Açıklama ve devre diyagramı için bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="91a66-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="91a66-123">Başvurular</span><span class="sxs-lookup"><span data-stu-id="91a66-123">References</span></span>

- [<span data-ttu-id="91a66-124">*Michael A. Nielsen, Isaac L. Chuang*, hisse hesaplaması ve hisse bilgisi</span><span class="sxs-lookup"><span data-stu-id="91a66-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="91a66-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="91a66-125">See Also</span></span>

- [<span data-ttu-id="91a66-126">Microsoft. hisse. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="91a66-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)