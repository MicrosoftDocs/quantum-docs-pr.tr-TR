---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Applyxcontroltadontruthtable işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 73d63936f02a52dfbbad7b8575110177a9e4463d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733930"
---
# <a name="applyxcontrolledontruthtable-operation"></a><span data-ttu-id="ea144-102">Applyxcontroltadontruthtable işlemi</span><span class="sxs-lookup"><span data-stu-id="ea144-102">ApplyXControlledOnTruthTable operation</span></span>

<span data-ttu-id="ea144-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ea144-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ea144-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ea144-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ea144-105">@"microsoft.quantum.intrinsic.x" `target` `func` İçindeki klasik atama için Boolean işlevi true olarak değerlendirilirse, işlemini üzerine uygular `controlRegister` .</span><span class="sxs-lookup"><span data-stu-id="ea144-105">Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.</span></span>

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="ea144-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ea144-106">Description</span></span>

<span data-ttu-id="ea144-107">İşlem, sırasıyla $x $ ve $y $ temsil eden Unitary işlemini \begin{hizalaması} U\ket {x} \ demet {y} = \ket{x}\ket{y \oplus f (x)} \end{hizalaması} uygular `controlRegister` `target` .</span><span class="sxs-lookup"><span data-stu-id="ea144-107">The operation implements the unitary operation \begin{align} U\ket{x}\ket{y} = \ket{x}\ket{y \oplus f(x)} \end{align} where $x$ and $y$ represent `controlRegister` and `target`, respectively.</span></span>

<span data-ttu-id="ea144-108">$F $ Boole işlevi, büyük bir tamsayı bakımından bir Truth tablosu olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="ea144-108">The Boolean function $f$ is represented as a truth table in terms of a big integer.</span></span>
<span data-ttu-id="ea144-109">Örneğin, üç giriş üzerindeki çoğunluk işlevi bitstring tarafından temsil edilir `11101000` . Bu, en önemli bitin `1` giriş atamasına karşılık geldiği `(1, 1, 1)` ve en az önemli bitin `0` giriş atamasına karşılık geldiği `(0, 0, 0)` bitdizedir.</span><span class="sxs-lookup"><span data-stu-id="ea144-109">For example, the majority function on three inputs is represented by the bitstring `11101000`, where the most significant bit `1` corresponds to the input assignment `(1, 1, 1)`, and the least significant bit `0` corresponds to the input assignment `(0, 0, 0)`.</span></span>
<span data-ttu-id="ea144-110">`0xE8L`Onaltılık gösterimde veya ondalık gösteriminde olduğu gibi büyük tamsayı ile temsil edilebilir `232L` .</span><span class="sxs-lookup"><span data-stu-id="ea144-110">It can be represented by the big integer `0xE8L` in hexadecimal notation or as `232L` in decimal notation.</span></span>  <span data-ttu-id="ea144-111">`L`Sonek, sabitin tür olduğunu gösterir `BigInt` .</span><span class="sxs-lookup"><span data-stu-id="ea144-111">The `L` suffix indicates that the constant is of type `BigInt`.</span></span>
<span data-ttu-id="ea144-112">Bu gösterim hakkında daha fazla ayrıntı aynı zamanda [Truth tabloları kükümi](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)'da bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="ea144-112">More details on this representation can also be found in the [truth tables kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).</span></span>

<span data-ttu-id="ea144-113">Uygulama ve kapıları kullanımını sağlar @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="ea144-113">The implementation makes use of @"microsoft.quantum.intrinsic.cnot" and @"microsoft.quantum.intrinsic.r1" gates.</span></span>

## <a name="input"></a><span data-ttu-id="ea144-114">Giriş</span><span class="sxs-lookup"><span data-stu-id="ea144-114">Input</span></span>

### <a name="func--bigint"></a><span data-ttu-id="ea144-115">Func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ea144-115">func : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ea144-116">Büyük tamsayı olarak temsil edilen Boolean Truth tablosu</span><span class="sxs-lookup"><span data-stu-id="ea144-116">Boolean truth table represented as big integer</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="ea144-117">controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ea144-117">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ea144-118">Denetim qubits 'i kaydetme</span><span class="sxs-lookup"><span data-stu-id="ea144-118">Register of control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ea144-119">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ea144-119">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ea144-120">Hedef qubit</span><span class="sxs-lookup"><span data-stu-id="ea144-120">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="ea144-121">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ea144-121">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ea144-122">Referanslar</span><span class="sxs-lookup"><span data-stu-id="ea144-122">References</span></span>

- [<span data-ttu-id="ea144-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arxıv: Quant-pH/0303063</span><span class="sxs-lookup"><span data-stu-id="ea144-123">*N. Schuch* , *J. Siewert* , PRL 91, no. 027902, 2003, arXiv:quant-ph/0303063</span></span>](https://arxiv.org/abs/quant-ph/0303063)
- [<span data-ttu-id="ea144-124">*Mathias Soeken* , *MARI Roetteler* , arxıv: 2005.12310</span><span class="sxs-lookup"><span data-stu-id="ea144-124">*Mathias Soeken* , *Martin Roetteler* , arXiv:2005.12310</span></span>](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a><span data-ttu-id="ea144-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ea144-125">See Also</span></span>

- [<span data-ttu-id="ea144-126">Microsoft. hisse. Sengıı. Applyxcontroltadontruthtablewithcleantarget</span><span class="sxs-lookup"><span data-stu-id="ea144-126">Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)