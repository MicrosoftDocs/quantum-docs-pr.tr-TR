---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842498"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="52252-102">StateOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="52252-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="52252-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="52252-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="52252-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="52252-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="52252-105">Bir Oracle türünü öğesine dönüştürür `DeterministicStateOracle` `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="52252-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="52252-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="52252-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="52252-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="52252-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="52252-108">Bir durum hazırlama Oracle $A $ türü `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="52252-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="52252-109">Çıkış: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="52252-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="52252-110">Aynı durum hazırlama Oracle $A $, ancak şimdi türü `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="52252-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="52252-111">Bu, içindeki bayrak dizininin `StateOracle` bir kukla değişken olduğunu ve hiçbir etkiye sahip olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="52252-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="52252-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="52252-112">See Also</span></span>

- [<span data-ttu-id="52252-113">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="52252-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="52252-114">Microsoft. hisse. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="52252-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)