---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentI
title: ContinuedFractionConvergentI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentI
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: 2322e005a5afb73d9719eb65d9ebf50740f1c9fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732751"
---
# <a name="continuedfractionconvergenti-function"></a><span data-ttu-id="6cdb6-102">ContinuedFractionConvergentI işlevi</span><span class="sxs-lookup"><span data-stu-id="6cdb6-102">ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="6cdb6-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6cdb6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6cdb6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6cdb6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6cdb6-105">`fraction`Paydadan daha az veya eşit olan en yakın devam eden kesir convergent 'ı bulur`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6cdb6-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentI (fraction : Microsoft.Quantum.Math.Fraction, denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="6cdb6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6cdb6-106">Input</span></span>

### <a name="fraction--fraction"></a><span data-ttu-id="6cdb6-107">kesir: [kesir](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="6cdb6-107">fraction : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="6cdb6-108">Nominal değeri: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cdb6-108">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="6cdb6-109">Çıkış: [kesir](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="6cdb6-109">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

<span data-ttu-id="6cdb6-110">`fraction`Paydaya daha az veya eşit olan en yakın sürekli kesir`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6cdb6-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>