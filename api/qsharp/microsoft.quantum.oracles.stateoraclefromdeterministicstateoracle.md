---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733343"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="6cde8-102">StateOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="6cde8-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="6cde8-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="6cde8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="6cde8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6cde8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6cde8-105">Bir Oracle türünü öğesine dönüştürür `DeterministicStateOracle` `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="6cde8-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="6cde8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6cde8-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="6cde8-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="6cde8-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="6cde8-108">Bir durum hazırlama Oracle $A $ türü `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="6cde8-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="6cde8-109">Çıkış: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="6cde8-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="6cde8-110">Aynı durum hazırlama Oracle $A $, ancak şimdi türü `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="6cde8-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="6cde8-111">Bu, içindeki bayrak dizininin `StateOracle` bir kukla değişken olduğunu ve hiçbir etkiye sahip olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="6cde8-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cde8-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6cde8-112">See Also</span></span>

- [<span data-ttu-id="6cde8-113">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="6cde8-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="6cde8-114">Microsoft. hisse. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="6cde8-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)