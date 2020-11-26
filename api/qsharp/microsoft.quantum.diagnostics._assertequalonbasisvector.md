---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213778"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="c250e-102">_assertEqualOnBasisVector işlemi</span><span class="sxs-lookup"><span data-stu-id="c250e-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="c250e-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c250e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c250e-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c250e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c250e-105">İki işlem `givenU` ve bir temel duruma uygulamanın sonucunun aynı olup olmadığını denetler `expectedU` .</span><span class="sxs-lookup"><span data-stu-id="c250e-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="c250e-106">Temel durum, `basis` parametresiyle açıklanır.</span><span class="sxs-lookup"><span data-stu-id="c250e-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="c250e-107"><xref:microsoft.quantum.extensions.fliptobasis>Bu açıklama hakkında daha fazla bilgi için bkz. işlev.</span><span class="sxs-lookup"><span data-stu-id="c250e-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c250e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c250e-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="c250e-109">temel: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c250e-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c250e-110">Her $n $ qubit için tek qubit tabanlı bir durum KIMLIĞI (0 <= kimlik <= 3) tarafından belirtilen temel durum.</span><span class="sxs-lookup"><span data-stu-id="c250e-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="c250e-111">givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c250e-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c250e-112">$N $ qubits üzerinde işlem denetlenecek.</span><span class="sxs-lookup"><span data-stu-id="c250e-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="c250e-113">expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="c250e-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c250e-114">GivenU 'nin karşılaştırılacağı $n $ qubits üzerinde başvuru işlemi.</span><span class="sxs-lookup"><span data-stu-id="c250e-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c250e-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c250e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

