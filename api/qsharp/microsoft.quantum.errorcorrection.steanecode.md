---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726990"
---
# <a name="steanecode-function"></a><span data-ttu-id="b3d04-102">SteaneCode işlevi</span><span class="sxs-lookup"><span data-stu-id="b3d04-102">SteaneCode function</span></span>

<span data-ttu-id="b3d04-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b3d04-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b3d04-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3d04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3d04-105">Yerinde sendromu ölçümünde ⟦ 7, 1, 3 ⟧ steane Code Encoder ve Decoder 'ı temsil eden bir CSS değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b3d04-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="b3d04-106">Çıkış: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="b3d04-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="b3d04-107">⟦ 7, 1, 3 ⟧ Steane kodu için kodlama ve hata düzeltme gerçekleştirmek üzere tüm ilgili verileri toplayan CSS türünde bir nesne.</span><span class="sxs-lookup"><span data-stu-id="b3d04-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3d04-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b3d04-108">Remarks</span></span>

<span data-ttu-id="b3d04-109">Bu kod aşağıdaki kağıda bulundu:</span><span class="sxs-lookup"><span data-stu-id="b3d04-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="b3d04-110">A.</span><span class="sxs-lookup"><span data-stu-id="b3d04-110">A.</span></span> <span data-ttu-id="b3d04-111">Steane, "çoklu parçacık girişim ve hisse hata düzeltmesi", proc.</span><span class="sxs-lookup"><span data-stu-id="b3d04-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="b3d04-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="b3d04-112">Roy.</span></span> <span data-ttu-id="b3d04-113">SOC. lond.</span><span class="sxs-lookup"><span data-stu-id="b3d04-113">Soc. Lond.</span></span> <span data-ttu-id="b3d04-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="b3d04-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>