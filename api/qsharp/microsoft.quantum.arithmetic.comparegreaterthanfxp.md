---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843317"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="4ece8-102">CompareGreaterThanFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="4ece8-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="4ece8-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4ece8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4ece8-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="4ece8-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="4ece8-105">Hisse Yazmaçları içinde depolanan iki sabit noktalı sayıyı karşılaştırır ve sonucu üzerinde bir çevir denetimi yapar.</span><span class="sxs-lookup"><span data-stu-id="4ece8-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4ece8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4ece8-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="4ece8-107">FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4ece8-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4ece8-108">Karşılaştırılacak ilk sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="4ece8-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="4ece8-109">FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="4ece8-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="4ece8-110">Karşılaştırılacak ikinci sabit noktalı sayı.</span><span class="sxs-lookup"><span data-stu-id="4ece8-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="4ece8-111">Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4ece8-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4ece8-112">Karşılaştırmanın sonucu.</span><span class="sxs-lookup"><span data-stu-id="4ece8-112">Result of the comparison.</span></span> <span data-ttu-id="4ece8-113">İse çevrilcektir `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="4ece8-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ece8-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ece8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4ece8-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4ece8-115">Remarks</span></span>

<span data-ttu-id="4ece8-116">Geçerli uygulama iki sabit noktalı sayının aynı nokta konumuna ve aynı sayıda qubit 'e sahip olmasını gerektirir.</span><span class="sxs-lookup"><span data-stu-id="4ece8-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>