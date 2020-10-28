---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732178"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="5bfc0-102">ReflectionOracleFromDeterministicStateOracle işlevi</span><span class="sxs-lookup"><span data-stu-id="5bfc0-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="5bfc0-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5bfc0-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5bfc0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bfc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bfc0-105">Bir Oracle 'dan belirli bir durum hakkında yansıma oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="5bfc0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5bfc0-106">Description</span></span>

<span data-ttu-id="5bfc0-107">Bir Unitary matrisi tarafından temsil edilen bir belirleyici durum hazırlama $O $, bu işlevin sonucu, Oracle $O $; tarafından hazırlanan $ \ket{\psı} $ durumunun etrafında bir yansıma uygulayan bir Oracle olur. diğer bir deyişle, $ \ket{\psı} $, $O {0} \tus= \ket{\psı} $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="5bfc0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="5bfc0-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="5bfc0-109">Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="5bfc0-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="5bfc0-110">$ \Ket{\psı} $ durumunun kopyalarını hazırlayan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="5bfc0-111">Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="5bfc0-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="5bfc0-112">$ \Ket{\psı} $ durumunu yansıtan bir Oracle.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bfc0-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-113">See Also</span></span>

- [<span data-ttu-id="5bfc0-114">Microsoft. hisse. Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="5bfc0-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="5bfc0-115">Microsoft. hisse. Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="5bfc0-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)