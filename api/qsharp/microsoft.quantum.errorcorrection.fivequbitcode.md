---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 3b45af29897735905f7fe52340e2a8e425bd8cbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200892"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="cfad0-102">FiveQubitCode işlevi</span><span class="sxs-lookup"><span data-stu-id="cfad0-102">FiveQubitCode function</span></span>

<span data-ttu-id="cfad0-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cfad0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cfad0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfad0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfad0-105">Yerinde sendromu ölçümlü ⟦ 5, 1, 3 ⟧ Code Encoder ve Decoder öğelerini temsil eden bir qecc değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="cfad0-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="cfad0-106">Çıkış: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="cfad0-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="cfad0-107">Bir tür belirterek hisse hata düzeltme kodunun bir uygulamasını döndürür `QECC` .</span><span class="sxs-lookup"><span data-stu-id="cfad0-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfad0-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cfad0-108">Remarks</span></span>

<span data-ttu-id="cfad0-109">Bu kod, aşağıdaki iki İnceleme içinde bağımsız olarak bulunur:</span><span class="sxs-lookup"><span data-stu-id="cfad0-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="cfad0-110">C.</span><span class="sxs-lookup"><span data-stu-id="cfad0-110">C.</span></span> <span data-ttu-id="cfad0-111">Olsun.</span><span class="sxs-lookup"><span data-stu-id="cfad0-111">H.</span></span> <span data-ttu-id="cfad0-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="cfad0-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="cfad0-113">Smolin ve W. K.</span><span class="sxs-lookup"><span data-stu-id="cfad0-113">Smolin and W. K.</span></span> <span data-ttu-id="cfad0-114">Wootters, "karışık durum entanglement ve hisse hata düzeltmesi," fiziksel. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 ve</span><span class="sxs-lookup"><span data-stu-id="cfad0-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="cfad0-115">Sağ.</span><span class="sxs-lookup"><span data-stu-id="cfad0-115">R.</span></span> <span data-ttu-id="cfad0-116">LaFlamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="cfad0-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="cfad0-117">Paz ve W. H.</span><span class="sxs-lookup"><span data-stu-id="cfad0-117">Paz and W. H.</span></span> <span data-ttu-id="cfad0-118">Zurek, "kusursuz hisse hata düzeltme kodu," fiziksel. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="cfad0-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="cfad0-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="cfad0-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>