---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729468"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="9893f-102">ApplyMultiControlledCA işlemi</span><span class="sxs-lookup"><span data-stu-id="9893f-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="9893f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9893f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9893f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9893f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9893f-105">Listedir denetimli bir işlemin çarpma denetimli bir sürümünü uygular.</span><span class="sxs-lookup"><span data-stu-id="9893f-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="9893f-106">Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="9893f-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9893f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="9893f-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="9893f-108">Singlycontroltadop: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="9893f-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="9893f-109">Tek bir qubit üzerinde denetlenen bir işlem.</span><span class="sxs-lookup"><span data-stu-id="9893f-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="9893f-110">İşlemin bağımsız değişkenindeki ilk qubit bir denetim olarak kabul edilir ve REST 'in hedef qubit olduğu varsayılır.</span><span class="sxs-lookup"><span data-stu-id="9893f-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="9893f-111">`ApplyMultiControlled` her zaman `singlyControlledOp` en az 1 uzunluğunda bir bağımsız değişkenle çağırır.</span><span class="sxs-lookup"><span data-stu-id="9893f-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="9893f-112">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="9893f-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="9893f-113">Oluşturma için kullanılacak kontrollü kontrollü olmayan ağ geçidi.</span><span class="sxs-lookup"><span data-stu-id="9893f-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="9893f-114">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9893f-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9893f-115">`singlyControlledOp`Üzerinde kontrol edilecek qubits.</span><span class="sxs-lookup"><span data-stu-id="9893f-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="9893f-116">Uzunluğu `controls` en az 1 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9893f-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="9893f-117">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9893f-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9893f-118">Üzerinde davranan hedef qubit `singlyControlledOp` .</span><span class="sxs-lookup"><span data-stu-id="9893f-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9893f-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9893f-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9893f-120">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9893f-120">Remarks</span></span>

<span data-ttu-id="9893f-121">Bu işlem yalnızca temiz bir anyenla qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="9893f-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="9893f-122">Açıklama ve devre diyagramı için bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang</span><span class="sxs-lookup"><span data-stu-id="9893f-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="9893f-123">Referanslar</span><span class="sxs-lookup"><span data-stu-id="9893f-123">References</span></span>

- [<span data-ttu-id="9893f-124">*Michael A. Nielsen, Isaac L. Chuang* , hisse hesaplaması ve hisse bilgisi</span><span class="sxs-lookup"><span data-stu-id="9893f-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="9893f-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9893f-125">See Also</span></span>

- [<span data-ttu-id="9893f-126">Microsoft. hisse. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="9893f-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)