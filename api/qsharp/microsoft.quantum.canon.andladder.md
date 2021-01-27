---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: d44c462c7a9fc9521bdecfe2ca7f607e90482baf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845217"
---
# <a name="andladder-operation"></a><span data-ttu-id="39fda-102">AndLadder işlemi</span><span class="sxs-lookup"><span data-stu-id="39fda-102">AndLadder operation</span></span>

<span data-ttu-id="39fda-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39fda-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39fda-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39fda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39fda-105">Hedef qubitleri kaydettirmek üzerinde denetimli bir "ve" el der "gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="39fda-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="39fda-106">Description</span><span class="sxs-lookup"><span data-stu-id="39fda-106">Description</span></span>

<span data-ttu-id="39fda-107">Bu işlem, aşağıdaki hesaplama tabanlı eşleme tarafından tanımlanan bir dönüşüm uygular, $ $ \begin{hizalaması} \ket{x \_ 1, \noktalar, x \_ n} \ket{y \_ 1, \noktalar, y \_ {n-1}} \mapsto \ket{x \_ 1, \noktalar, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \noktalar, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cnoktalar \land x \_ {n-1}}, \end{hizalaması} $ $, $ \ket{x \_ 1, \noktalar, x \_ n} $, ' nin hesaplama tabanlı durumlarına `controls` ve $ \ket{y \_ 1, \noktalar, y \_ {n-1}} $ öğesinin hesaplama tabanlı durumlarına başvurur `targets` .</span><span class="sxs-lookup"><span data-stu-id="39fda-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="39fda-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="39fda-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="39fda-109">ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="39fda-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="39fda-110">Oluşturma için kullanılacak CCNOT kapısı.</span><span class="sxs-lookup"><span data-stu-id="39fda-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="39fda-111">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39fda-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39fda-112">Ve merdiveni için denetim olarak kullanılacak qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="39fda-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="39fda-113">Bu işlem, sabit durum hesaplama durumlarını bırakır `controls` .</span><span class="sxs-lookup"><span data-stu-id="39fda-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="39fda-114">Uzunluğu `controls` en az 2 olmalı ve uzunluğu ve uzunluğuna eşit olmalıdır `targets` .</span><span class="sxs-lookup"><span data-stu-id="39fda-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="39fda-115">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="39fda-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="39fda-116">Uzunluğu `targets` en az 1, eksi bir uzunluk uzunluğuna eşit olmalıdır `controls` .</span><span class="sxs-lookup"><span data-stu-id="39fda-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39fda-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39fda-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39fda-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="39fda-118">Remarks</span></span>

- <span data-ttu-id="39fda-119">Ve ' ın bir parçası olarak kullanılır <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="39fda-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="39fda-120">Açıklama ve devre diyagramı için, bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang.</span><span class="sxs-lookup"><span data-stu-id="39fda-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="39fda-121">Başvurular</span><span class="sxs-lookup"><span data-stu-id="39fda-121">References</span></span>

- [<span data-ttu-id="39fda-122">*Michael A. Nielsen, Isaac L. Chuang*, hisse hesaplaması ve hisse bilgisi</span><span class="sxs-lookup"><span data-stu-id="39fda-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)