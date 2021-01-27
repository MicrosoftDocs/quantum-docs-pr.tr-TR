---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Çoğullysi işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 7c7e7dfaee9b9dc717db44956506984e60281dd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843006"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="5e303-102">Çoğullysi işlemi</span><span class="sxs-lookup"><span data-stu-id="5e303-102">MultiplySI operation</span></span>

<span data-ttu-id="5e303-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5e303-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5e303-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5e303-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5e303-105">İmzalanan tamsayıyı `xs` işaretli tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.</span><span class="sxs-lookup"><span data-stu-id="5e303-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5e303-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5e303-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="5e303-107">xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e303-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5e303-108">n bit çoğullıve (Signedlitttaendian)</span><span class="sxs-lookup"><span data-stu-id="5e303-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="5e303-109">YS: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e303-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5e303-110">n bit çarpanı (Signedlitttaendian)</span><span class="sxs-lookup"><span data-stu-id="5e303-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="5e303-111">Sonuç: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e303-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5e303-112">2N bit sonucu (Signedlitttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="5e303-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e303-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e303-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

