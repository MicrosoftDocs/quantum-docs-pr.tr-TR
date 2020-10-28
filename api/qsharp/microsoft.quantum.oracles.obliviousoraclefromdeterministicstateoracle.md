---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732202"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="c1527-102">ObliviousOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="c1527-102">ObliviousOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="c1527-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c1527-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c1527-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1527-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1527-105">Oracles ve birleştirir `DeterministicStateOracle` `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="c1527-105">Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.</span></span>

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a><span data-ttu-id="c1527-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c1527-106">Input</span></span>

### <a name="ancillaoracle--deterministicstateoracle"></a><span data-ttu-id="c1527-107">Anlanlaoracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="c1527-107">ancillaOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="c1527-108">Bir durum hazırlama Oracle $A $, `DeterministicStateOracle` kayıt $a $ üzerinde işlem gören tür $.</span><span class="sxs-lookup"><span data-stu-id="c1527-108">A state preparation oracle $A$ of type `DeterministicStateOracle` acting on register $a$.</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="c1527-109">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="c1527-109">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="c1527-110">`ObliviousOracle`Kayıt $a, s $ üzerinde ortaklaşa çalışan bir oracle $U $ türü.</span><span class="sxs-lookup"><span data-stu-id="c1527-110">A oracle $U$ of type `ObliviousOracle` acting jointly on register $a,s$.</span></span>



## <a name="output--obliviousoracle"></a><span data-ttu-id="c1527-111">Çıkış: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="c1527-111">Output : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="c1527-112">Bir Oracle $O = UA $ türü `ObliviousOracle` .</span><span class="sxs-lookup"><span data-stu-id="c1527-112">An oracle $O=UA$ of type `ObliviousOracle`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1527-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c1527-113">See Also</span></span>

- [<span data-ttu-id="c1527-114">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="c1527-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="c1527-115">Microsoft. hisse. Oracles. ObliviousOracle</span><span class="sxs-lookup"><span data-stu-id="c1527-115">Microsoft.Quantum.Oracles.ObliviousOracle</span></span>](xref:Microsoft.Quantum.Oracles.ObliviousOracle)