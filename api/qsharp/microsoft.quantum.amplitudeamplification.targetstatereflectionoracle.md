---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Targetstatereflictionoracle işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191117"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="1e93f-102">Targetstatereflictionoracle işlevi</span><span class="sxs-lookup"><span data-stu-id="1e93f-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="1e93f-103">Ad alanı: [Microsoft. hisse. yükseltilmiş Tudeamplif](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="1e93f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="1e93f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e93f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e93f-105">`ReflectionOracle`Benzersiz olarak bayrak qubit tarafından işaretlenen hedef durumu hakkında bir oluşturur.</span><span class="sxs-lookup"><span data-stu-id="1e93f-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="1e93f-106">Hedef durumu 1 olarak ayarlanmış tek bir qubit ve diğerleri 0: $ \ demet {1} _F $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="1e93f-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="1e93f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="1e93f-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="1e93f-108">ıdxflagqubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e93f-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e93f-109">Oracle 'ın $f $ ' nin işaret edeceği dizin.</span><span class="sxs-lookup"><span data-stu-id="1e93f-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="1e93f-110">Çıkış: [Reflectionoracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="1e93f-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="1e93f-111">`ReflectionOracle`$ \Ket _F $ tarafından işaretlenen durumu yansıtan bir {1} .</span><span class="sxs-lookup"><span data-stu-id="1e93f-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e93f-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1e93f-112">See Also</span></span>

- [<span data-ttu-id="1e93f-113">Microsoft. hisse. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="1e93f-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)