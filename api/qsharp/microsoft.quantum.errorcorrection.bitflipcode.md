---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201232"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="6c399-102">BitFlipCode işlevi</span><span class="sxs-lookup"><span data-stu-id="6c399-102">BitFlipCode function</span></span>

<span data-ttu-id="6c399-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6c399-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6c399-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c399-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c399-105">Yerinde sendromu ölçümünde ⟦ 3, 1, 1 ⟧ bit çevirme kodu Kodlayıcısı ve kod çözücüsünü temsil eden bir qecc değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="6c399-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="6c399-106">Çıkış: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="6c399-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="6c399-107">Bir tür belirterek hisse hata düzeltme kodunun bir uygulamasını döndürür `QECC` .</span><span class="sxs-lookup"><span data-stu-id="6c399-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>