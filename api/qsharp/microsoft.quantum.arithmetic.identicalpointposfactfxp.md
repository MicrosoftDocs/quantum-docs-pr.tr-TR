---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731514"
---
# <a name="identicalpointposfactfxp-function"></a><span data-ttu-id="99ad6-102">IdenticalPointPosFactFxP işlevi</span><span class="sxs-lookup"><span data-stu-id="99ad6-102">IdenticalPointPosFactFxP function</span></span>

<span data-ttu-id="99ad6-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="99ad6-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="99ad6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99ad6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="99ad6-105">Belirtilen dizide bulunan tüm sabit noktalı sayıların, en az önemli bir bit sayılarak aynı nokta konumlarına sahip olması onayı.</span><span class="sxs-lookup"><span data-stu-id="99ad6-105">Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit.</span></span> <span data-ttu-id="99ad6-106">Yani, dizideki tüm sabit noktalı sayılar için bit eksi nokta konumu sayısının sabit olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="99ad6-106">I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.</span></span>

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="99ad6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="99ad6-107">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="99ad6-108">Sabit noktaları: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="99ad6-108">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="99ad6-109">Uyumluluk için denetlenecek hisse sabit noktalı sayıların dizisi (onaylama işlemleri kullanılarak).</span><span class="sxs-lookup"><span data-stu-id="99ad6-109">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="99ad6-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99ad6-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

