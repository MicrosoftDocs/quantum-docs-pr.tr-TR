---
uid: Microsoft.Quantum.Arithmetic.MultiplySI
title: Çoğullysi işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplySI
qsharp.summary: Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.
ms.openlocfilehash: 9ca781cbe90a8ec13e6a85a5babaf043bc8f2b5b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730602"
---
# <a name="multiplysi-operation"></a><span data-ttu-id="48f84-102">Çoğullysi işlemi</span><span class="sxs-lookup"><span data-stu-id="48f84-102">MultiplySI operation</span></span>

<span data-ttu-id="48f84-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="48f84-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="48f84-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48f84-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48f84-105">İmzalanan tamsayıyı `xs` işaretli tamsayı ile çarpın `ys` ve sonucu `result` , başlangıçta sıfır olması gereken ' de saklayın.</span><span class="sxs-lookup"><span data-stu-id="48f84-105">Multiply signed integer `xs` by signed integer `ys` and store the result in `result`, which must be zero initially.</span></span>

```qsharp
operation MultiplySI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Microsoft.Quantum.Arithmetic.SignedLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="48f84-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="48f84-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="48f84-107">xs: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48f84-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="48f84-108">n bit çoğullıve (Signedlitttaendian)</span><span class="sxs-lookup"><span data-stu-id="48f84-108">n-bit multiplicand (SignedLittleEndian)</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="48f84-109">YS: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48f84-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="48f84-110">n bit çarpanı (Signedlitttaendian)</span><span class="sxs-lookup"><span data-stu-id="48f84-110">n-bit multiplier (SignedLittleEndian)</span></span>


### <a name="result--signedlittleendian"></a><span data-ttu-id="48f84-111">Sonuç: [Signedlitttaendian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="48f84-111">result : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="48f84-112">2N bit sonucu (Signedlitttaendian), başlangıçta $ \ket $ durumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="48f84-112">2n-bit result (SignedLittleEndian), must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="48f84-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="48f84-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

