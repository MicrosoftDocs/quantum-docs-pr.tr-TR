---
uid: Microsoft.Quantum.ErrorCorrection.CSS
title: CSS Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: CSS
qsharp.summary: Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.
ms.openlocfilehash: c5227c771ec2c7c81d05a28681745af641eebeaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727122"
---
# <a name="css-user-defined-type"></a><span data-ttu-id="2c1b6-102">CSS Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="2c1b6-102">CSS user defined type</span></span>

<span data-ttu-id="2c1b6-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="2c1b6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="2c1b6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2c1b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2c1b6-105">Kodlayıcının, kod çözücüsünün ve hata için daha önce eşitleme ölçüm yordamları ve hatalara göre tanımlanan bir Calderbank – Shor – Steane (CSS) kodunu temsil eder `X` `Z` .</span><span class="sxs-lookup"><span data-stu-id="2c1b6-105">Represents a Calderbank–Shor–Steane (CSS) code as defined by its encoder, decoder, and its syndrome measurement procedures for `X` and `Z` errors, respectively.</span></span>

```qsharp

newtype CSS = (Microsoft.Quantum.ErrorCorrection.EncodeOp, Microsoft.Quantum.ErrorCorrection.DecodeOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp, Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp);
```

