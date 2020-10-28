---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: ComputeReciprocalI işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: b99e816ed69af6e6d1758442d6f95c5ab0e5c07a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731586"
---
# <a name="computereciprocali-operation"></a><span data-ttu-id="dc343-102">ComputeReciprocalI işlemi</span><span class="sxs-lookup"><span data-stu-id="dc343-102">ComputeReciprocalI operation</span></span>

<span data-ttu-id="dc343-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="dc343-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="dc343-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dc343-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dc343-105">Tamsayı bölme kullanılarak işaretsiz bir tamsayı x için karşılıklı 1/x hesaplar.</span><span class="sxs-lookup"><span data-stu-id="dc343-105">Computes the reciprocal 1/x for an unsigned integer x using integer division.</span></span> <span data-ttu-id="dc343-106">Sonuç, bir tamsayı olarak yorumlanır `floor(2^(2*n-1) / x)` .</span><span class="sxs-lookup"><span data-stu-id="dc343-106">The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.</span></span>

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="dc343-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="dc343-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="dc343-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc343-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dc343-109">n bit işaretsiz tamsayı</span><span class="sxs-lookup"><span data-stu-id="dc343-109">n-bit unsigned integer</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="dc343-110">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc343-110">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dc343-111">2N-bit çıkış, başlangıçta $ \ket $ konumunda olmalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="dc343-111">2n-bit output, must be in $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc343-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc343-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dc343-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dc343-113">Remarks</span></span>

<span data-ttu-id="dc343-114">X = 0 girişi için çıkış hepsi olur.</span><span class="sxs-lookup"><span data-stu-id="dc343-114">For the input x=0, the output will be all-ones.</span></span>