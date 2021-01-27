---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853067"
---
# <a name="steanecode-function"></a><span data-ttu-id="b54dc-102">SteaneCode işlevi</span><span class="sxs-lookup"><span data-stu-id="b54dc-102">SteaneCode function</span></span>

<span data-ttu-id="b54dc-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b54dc-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b54dc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b54dc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b54dc-105">Yerinde sendromu ölçümünde ⟦ 7, 1, 3 ⟧ steane Code Encoder ve Decoder 'ı temsil eden bir CSS değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="b54dc-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="b54dc-106">Çıkış: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="b54dc-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="b54dc-107">⟦ 7, 1, 3 ⟧ Steane kodu için kodlama ve hata düzeltme gerçekleştirmek üzere tüm ilgili verileri toplayan CSS türünde bir nesne.</span><span class="sxs-lookup"><span data-stu-id="b54dc-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b54dc-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b54dc-108">Remarks</span></span>

<span data-ttu-id="b54dc-109">Bu kod aşağıdaki kağıda bulundu:</span><span class="sxs-lookup"><span data-stu-id="b54dc-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="b54dc-110">A.</span><span class="sxs-lookup"><span data-stu-id="b54dc-110">A.</span></span> <span data-ttu-id="b54dc-111">Steane, "çoklu parçacık girişim ve hisse hata düzeltmesi", proc.</span><span class="sxs-lookup"><span data-stu-id="b54dc-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="b54dc-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="b54dc-112">Roy.</span></span> <span data-ttu-id="b54dc-113">SOC. lond.</span><span class="sxs-lookup"><span data-stu-id="b54dc-113">Soc. Lond.</span></span> <span data-ttu-id="b54dc-114">A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="b54dc-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>