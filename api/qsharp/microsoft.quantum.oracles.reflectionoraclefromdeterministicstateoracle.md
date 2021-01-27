---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842522"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="aa626-102">ReflectionOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="aa626-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="aa626-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="aa626-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="aa626-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa626-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa626-105">Bir Oracle 'dan belirli bir durum hakkında yansıma oluşturur.</span><span class="sxs-lookup"><span data-stu-id="aa626-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="aa626-106">Description</span><span class="sxs-lookup"><span data-stu-id="aa626-106">Description</span></span>

<span data-ttu-id="aa626-107">Bir Unitary matrisi tarafından temsil edilen bir belirleyici durum hazırlama $O $, bu işlevin sonucu, Oracle $O $; tarafından hazırlanan $ \ket{\psı} $ durumunun etrafında bir yansıma uygulayan bir Oracle olur. diğer bir deyişle, $ \ket{\psı} $, $O {0} \tus= \ket{\psı} $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="aa626-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="aa626-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="aa626-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="aa626-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="aa626-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="aa626-110">$ \Ket{\psı} $ durumunun kopyalarını hazırlayan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="aa626-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="aa626-111">Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="aa626-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="aa626-112">$ \Ket{\psı} $ durumunu yansıtan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="aa626-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa626-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="aa626-113">See Also</span></span>

- [<span data-ttu-id="aa626-114">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="aa626-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="aa626-115">Microsoft. hisse. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="aa626-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)