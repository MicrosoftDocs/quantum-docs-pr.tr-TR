---
uid: Microsoft.Quantum.Arithmetic.MultiplyI
title: Çoğullyi işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyI
qsharp.summary: Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7b44f64fdddfd95f51683c2c3b2f4d37d0cf6841
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730610"
---
# <a name="multiplyi-operation"></a><span data-ttu-id="d4414-102">Çoğullyi işlemi</span><span class="sxs-lookup"><span data-stu-id="d4414-102">MultiplyI operation</span></span>

<span data-ttu-id="d4414-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d4414-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d4414-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4414-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4414-105">Tamsayıyı `xs` tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.</span><span class="sxs-lookup"><span data-stu-id="d4414-105">Multiply integer `xs` by integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplyI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="d4414-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d4414-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d4414-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4414-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4414-108">$n $-bit çoğullıve (Litttaendian)</span><span class="sxs-lookup"><span data-stu-id="d4414-108">$n$-bit multiplicand (LittleEndian)</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d4414-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4414-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4414-110">$n $ bit çarpanı (Littliendian)</span><span class="sxs-lookup"><span data-stu-id="d4414-110">$n$-bit multiplier (LittleEndian)</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="d4414-111">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4414-111">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4414-112">$2N $-bit sonucu (Litttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="d4414-112">$2n$-bit result (LittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4414-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4414-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d4414-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d4414-114">Remarks</span></span>

<span data-ttu-id="d4414-115">Çarpma uygulamak için standart bir kaydırma ve ekleme yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="d4414-115">Uses a standard shift-and-add approach to implement the multiplication.</span></span>
<span data-ttu-id="d4414-116">Denetlenen sürüm, $x _i $ ' ı Control qubits üzerinde bir anment quge 'ya kopyalayarak ve sonra da anment qubit üzerinde ek bir şekilde denetlenerek geliştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="d4414-116">The controlled version was improved by copying out $x_i$ to an ancilla qubit conditioned on the control qubits, and then controlling the addition on the ancilla qubit.</span></span>