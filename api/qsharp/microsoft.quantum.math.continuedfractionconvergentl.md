---
uid: Microsoft.Quantum.Math.ContinuedFractionConvergentL
title: ContinuedFractionConvergentL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ContinuedFractionConvergentL
qsharp.summary: Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`
ms.openlocfilehash: a02b38fedb5b0025f04e7bba86f2f998493206b3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733119"
---
# <a name="continuedfractionconvergentl-function"></a><span data-ttu-id="958b8-102">ContinuedFractionConvergentL işlevi</span><span class="sxs-lookup"><span data-stu-id="958b8-102">ContinuedFractionConvergentL function</span></span>

<span data-ttu-id="958b8-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="958b8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="958b8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="958b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="958b8-105">`fraction`Paydadan daha az veya eşit olan en yakın devam eden kesir convergent 'ı bulur`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="958b8-105">Finds the continued fraction convergent closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>

```qsharp
function ContinuedFractionConvergentL (fraction : Microsoft.Quantum.Math.BigFraction, denominatorBound : BigInt) : Microsoft.Quantum.Math.BigFraction
```


## <a name="input"></a><span data-ttu-id="958b8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="958b8-106">Input</span></span>

### <a name="fraction--bigfraction"></a><span data-ttu-id="958b8-107">kesir: [Bigkesir](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="958b8-107">fraction : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>




### <a name="denominatorbound--bigint"></a><span data-ttu-id="958b8-108">Yınatorlimit: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="958b8-108">denominatorBound : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigfraction"></a><span data-ttu-id="958b8-109">Çıkış: [Bigkesir](xref:Microsoft.Quantum.Math.BigFraction)</span><span class="sxs-lookup"><span data-stu-id="958b8-109">Output : [BigFraction](xref:Microsoft.Quantum.Math.BigFraction)</span></span>

<span data-ttu-id="958b8-110">`fraction`Paydaya daha az veya eşit olan en yakın sürekli kesir`denominatorBound`</span><span class="sxs-lookup"><span data-stu-id="958b8-110">Continued fraction closest to `fraction` with the denominator less or equal to `denominatorBound`</span></span>