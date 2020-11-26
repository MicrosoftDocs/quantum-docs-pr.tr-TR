---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: c10fcbbe63d3d4c7d6c56196768c1062be1ca350
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210939"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="6803a-102">ContinuedFractionConvergentL işlevi</span><span class="sxs-lookup"><span data-stu-id="6803a-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="6803a-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="6803a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="6803a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6803a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6803a-105">`fraction`Paydadan daha az veya eşit olan en yakın devam eden kesir convergent 'ı bulur`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6803a-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="6803a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6803a-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="6803a-107">kesir: [Bigkesir](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="6803a-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="6803a-108">Yınatorlimit: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6803a-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="6803a-109">Çıkış: [Bigkesir](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="6803a-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="6803a-110">`fraction`Paydaya daha az veya eşit olan en yakın sürekli kesir`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="6803a-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>