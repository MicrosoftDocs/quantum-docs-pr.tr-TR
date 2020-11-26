---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Çoğullyi işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 96922f0147788b37cc9bace5154288a722d4ba95
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222516"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="5a853-102">Çoğullyi işlemi</span><span class="sxs-lookup"><span data-stu-id="5a853-102">MultiplyI operation</span></span>

<span data-ttu-id="5a853-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5a853-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5a853-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5a853-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5a853-105">Tamsayıyı `xs` tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.</span><span class="sxs-lookup"><span data-stu-id="5a853-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a853-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5a853-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5a853-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a853-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a853-108">$n $-bit çoğullıve (Litttaendian)</span><span class="sxs-lookup"><span data-stu-id="5a853-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="5a853-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a853-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a853-110">$n $ bit çarpanı (Littliendian)</span><span class="sxs-lookup"><span data-stu-id="5a853-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="5a853-111">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a853-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a853-112">$2N $-bit sonucu (Litttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="5a853-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a853-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a853-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5a853-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5a853-114">Remarks</span></span>

<span data-ttu-id="5a853-115">Çarpma uygulamak için standart bir kaydırma ve ekleme yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="5a853-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="5a853-116">Denetlenen sürüm, $x _i $ ' ı Control qubits üzerinde bir anment quge 'ya kopyalayarak ve sonra da anment qubit üzerinde ek bir şekilde denetlenerek geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="5a853-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>