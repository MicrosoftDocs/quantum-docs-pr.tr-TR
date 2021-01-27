---
uid: Microsoft.Quantum.Arithmetic.IdenticalFormatFactFxP
title: IdenticalFormatFactFxP işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalFormatFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.
ms.openlocfilehash: e9fed13348583c8f403b733dea787b42856816c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843184"
---
# <a name="identicalformatfactfxp-function"></a><span data-ttu-id="8b4e7-102">IdenticalFormatFactFxP işlevi</span><span class="sxs-lookup"><span data-stu-id="8b4e7-102">IdenticalFormatFactFxP function</span></span>

<span data-ttu-id="8b4e7-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8b4e7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8b4e7-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8b4e7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8b4e7-105">Belirtilen dizide bulunan tüm sabit noktalı sayıların, aynı nokta konumlarına ve qubit numaralarına sahip olması onayı.</span><span class="sxs-lookup"><span data-stu-id="8b4e7-105">Assert that all fixed-point numbers in the provided array have identical point positions and qubit numbers.</span></span>

```qsharp
function IdenticalFormatFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a><span data-ttu-id="8b4e7-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8b4e7-106">Input</span></span>

### <a name="fixedpoints--fixedpoint"></a><span data-ttu-id="8b4e7-107">Sabit noktaları: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span><span class="sxs-lookup"><span data-stu-id="8b4e7-107">fixedPoints : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]</span></span>

<span data-ttu-id="8b4e7-108">Uyumluluk için denetlenecek hisse sabit noktalı sayıların dizisi (onaylama işlemleri kullanılarak).</span><span class="sxs-lookup"><span data-stu-id="8b4e7-108">Array of quantum fixed-point numbers that will be checked for compatibility (using assertions).</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b4e7-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b4e7-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

