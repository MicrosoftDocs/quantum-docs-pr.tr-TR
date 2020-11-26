---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191049"
---
# <a name="addfxp-operation"></a><span data-ttu-id="c727b-102">AddFxP işlemi</span><span class="sxs-lookup"><span data-stu-id="c727b-102">AddFxP operation</span></span>

<span data-ttu-id="c727b-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c727b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c727b-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="c727b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="c727b-105">Hisse Yazmaçları içinde depolanan iki sabit noktalı sayıyı ekler.</span><span class="sxs-lookup"><span data-stu-id="c727b-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c727b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c727b-106">Description</span></span>

<span data-ttu-id="c727b-107">$ \Ket{f_1} $ ve $ \ket{f_2} $ durumlarında sırasıyla iki sabit noktalı kayıt verildiğinde, $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $ işlemini gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="c727b-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="c727b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="c727b-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="c727b-109">FP1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c727b-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c727b-110">İlk sabit noktalı sayı</span><span class="sxs-lookup"><span data-stu-id="c727b-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="c727b-111">FP2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c727b-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c727b-112">İkinci sabit noktalı sayı, iki girişin toplamını içerecek şekilde güncelleştirilecektir.</span><span class="sxs-lookup"><span data-stu-id="c727b-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c727b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c727b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c727b-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c727b-114">Remarks</span></span>

<span data-ttu-id="c727b-115">Geçerli uygulama iki sabit noktalı sayının aynı nokta konumunun, en az önemli bitden ($n _i $ ve $p _i $ eşit olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c727b-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>