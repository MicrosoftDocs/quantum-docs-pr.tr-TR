---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727061"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="cb97e-102">FiveQubitCode işlevi</span><span class="sxs-lookup"><span data-stu-id="cb97e-102">FiveQubitCode function</span></span>

<span data-ttu-id="cb97e-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cb97e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cb97e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb97e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb97e-105">Yerinde sendromu ölçümlü ⟦ 5, 1, 3 ⟧ Code Encoder ve Decoder öğelerini temsil eden bir qecc değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="cb97e-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="cb97e-106">Çıkış: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="cb97e-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="cb97e-107">Bir tür belirterek hisse hata düzeltme kodunun bir uygulamasını döndürür `QECC` .</span><span class="sxs-lookup"><span data-stu-id="cb97e-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb97e-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cb97e-108">Remarks</span></span>

<span data-ttu-id="cb97e-109">Bu kod, aşağıdaki iki İnceleme içinde bağımsız olarak bulunur:</span><span class="sxs-lookup"><span data-stu-id="cb97e-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="cb97e-110">C.</span><span class="sxs-lookup"><span data-stu-id="cb97e-110">C.</span></span> <span data-ttu-id="cb97e-111">Olsun.</span><span class="sxs-lookup"><span data-stu-id="cb97e-111">H.</span></span> <span data-ttu-id="cb97e-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="cb97e-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="cb97e-113">Smolin ve W. K.</span><span class="sxs-lookup"><span data-stu-id="cb97e-113">Smolin and W. K.</span></span> <span data-ttu-id="cb97e-114">Wootters, "karışık durum entanglement ve hisse hata düzeltmesi," fiziksel. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 ve</span><span class="sxs-lookup"><span data-stu-id="cb97e-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="cb97e-115">Sağ.</span><span class="sxs-lookup"><span data-stu-id="cb97e-115">R.</span></span> <span data-ttu-id="cb97e-116">LaFlamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="cb97e-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="cb97e-117">Paz ve W. H.</span><span class="sxs-lookup"><span data-stu-id="cb97e-117">Paz and W. H.</span></span> <span data-ttu-id="cb97e-118">Zurek, "kusursuz hisse hata düzeltme kodu," fiziksel. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="cb97e-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="cb97e-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="cb97e-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>