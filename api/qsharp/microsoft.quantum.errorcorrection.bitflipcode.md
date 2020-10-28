---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 8d4498647682026e9dec3fa96cfb69ba1e3214b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727128"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="039e9-102">BitFlipCode işlevi</span><span class="sxs-lookup"><span data-stu-id="039e9-102">BitFlipCode function</span></span>

<span data-ttu-id="039e9-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="039e9-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="039e9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="039e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="039e9-105">Yerinde sendromu ölçümünde ⟦ 3, 1, 1 ⟧ bit çevirme kodu Kodlayıcısı ve kod çözücüsünü temsil eden bir qecc değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="039e9-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="039e9-106">Çıkış: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="039e9-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="039e9-107">Bir tür belirterek hisse hata düzeltme kodunun bir uygulamasını döndürür `QECC` .</span><span class="sxs-lookup"><span data-stu-id="039e9-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>