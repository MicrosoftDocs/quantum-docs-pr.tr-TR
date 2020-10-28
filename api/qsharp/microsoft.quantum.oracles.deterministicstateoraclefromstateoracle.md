---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733362"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="82c4e-102">DeterministicStateOracleFromStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="82c4e-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="82c4e-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="82c4e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="82c4e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82c4e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82c4e-105">Bir Oracle türünü öğesine dönüştürür `StateOracle` `DeterministicStateOracle` .</span><span class="sxs-lookup"><span data-stu-id="82c4e-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="82c4e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="82c4e-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="82c4e-107">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82c4e-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82c4e-108">`stateOracle`İki kayıt üzerinde açıkça işlem gören $A $ bayrağının işaret eden dizin: $f $ bayrağı ve system $s $, örneğin $A {0} \_ \tusf\tus{\ PSI} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="82c4e-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="82c4e-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="82c4e-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="82c4e-110">Bir durum hazırlama Oracle $A $ türü `StateOracle` .</span><span class="sxs-lookup"><span data-stu-id="82c4e-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="82c4e-111">Çıkış: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="82c4e-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="82c4e-112">Aynı durum hazırlama Oracle $A $, ancak artık `DeterministicStateOracle` Bu nedenle, $a, s $ artık açıkça ayrısız bir kayıt üzerinde davranır, ör.  $A \ket{0\psı} \_ {as} $.</span><span class="sxs-lookup"><span data-stu-id="82c4e-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="82c4e-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="82c4e-113">See Also</span></span>

- [<span data-ttu-id="82c4e-114">Microsoft. hisse. Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="82c4e-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="82c4e-115">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="82c4e-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)