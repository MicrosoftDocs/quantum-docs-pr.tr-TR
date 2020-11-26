---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: d37bf1c10899d06e798d29c68f88b06f2d5918a9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195571"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="7b119-102">ContinuedFractionConvergentI işlevi</span><span class="sxs-lookup"><span data-stu-id="7b119-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="7b119-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7b119-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7b119-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b119-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b119-105">`fraction`Paydadan daha az veya eşit olan en yakın devam eden kesir convergent 'ı bulur`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="7b119-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="7b119-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7b119-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="7b119-107">kesir: [kesir](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="7b119-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="7b119-108">Nominal değeri: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7b119-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="7b119-109">Çıkış: [kesir](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="7b119-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="7b119-110">`fraction`Paydaya daha az veya eşit olan en yakın sürekli kesir`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="7b119-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>