---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731815"
---
# <a name="applyoutercdkmadder-operation"></a><span data-ttu-id="78775-102">ApplyOuterCDKMAdder işlemi</span><span class="sxs-lookup"><span data-stu-id="78775-102">ApplyOuterCDKMAdder operation</span></span>

<span data-ttu-id="78775-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="78775-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="78775-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78775-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78775-105">Aşağıdaki tamsayı ekleme işleminde kullanılan, geri döndürülebilir ve yerinde Ripple-taşıma işlemi aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="78775-105">Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below.</span></span>
<span data-ttu-id="78775-106">İki qubit kaydı `xs` ve `ys` aynı uzunlukta olmak üzere, bu işlem, içindeki QUBIT 'ler içeren bir RIPPLE ve ccnot kapısı sırası uygular ve bu, `xs` `ys` hedef olarak içinde denetimler ve qubits olarak sunulur `xs` .</span><span class="sxs-lookup"><span data-stu-id="78775-106">Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.</span></span>

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="78775-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="78775-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="78775-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="78775-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="78775-109">İlk qubit kayıt, denetimleri ve hedefleri içerir.</span><span class="sxs-lookup"><span data-stu-id="78775-109">First qubit register, containing controls and targets.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="78775-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="78775-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="78775-111">, Denetimlere katkıda bulunan ikinci qubit kayıt.</span><span class="sxs-lookup"><span data-stu-id="78775-111">Second qubit register, contributing to the controls.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="78775-112">anyalanla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78775-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78775-113">Bu işleme, Ripptacarryaddercdkm içinde kullanılan anella qubit.</span><span class="sxs-lookup"><span data-stu-id="78775-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78775-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78775-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="78775-115">Referanslar</span><span class="sxs-lookup"><span data-stu-id="78775-115">References</span></span>

- <span data-ttu-id="78775-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse</span><span class="sxs-lookup"><span data-stu-id="78775-116">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1