---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193837"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="760bb-102">ReflectionOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="760bb-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="760bb-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="760bb-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="760bb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="760bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="760bb-105">Bir Oracle 'dan belirli bir durum hakkında yansıma oluşturur.</span><span class="sxs-lookup"><span data-stu-id="760bb-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="760bb-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="760bb-106">Description</span></span>

<span data-ttu-id="760bb-107">Bir Unitary matrisi tarafından temsil edilen bir belirleyici durum hazırlama $O $, bu işlevin sonucu, Oracle $O $; tarafından hazırlanan $ \ket{\psı} $ durumunun etrafında bir yansıma uygulayan bir Oracle olur. diğer bir deyişle, $ \ket{\psı} $, $O {0} \tus= \ket{\psı} $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="760bb-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="760bb-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="760bb-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="760bb-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="760bb-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="760bb-110">$ \Ket{\psı} $ durumunun kopyalarını hazırlayan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="760bb-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="760bb-111">Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="760bb-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="760bb-112">$ \Ket{\psı} $ durumunu yansıtan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="760bb-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="760bb-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="760bb-113">See Also</span></span>

- [<span data-ttu-id="760bb-114">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="760bb-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="760bb-115">Microsoft. hisse. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="760bb-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)