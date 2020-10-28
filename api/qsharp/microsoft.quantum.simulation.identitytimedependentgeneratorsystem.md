---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: Identitytimedependentgeneratorsystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: d51794aacbcf13ab567ff6be4f5d6b04581833bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733514"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="72349-102">Identitytimedependentgeneratorsystem işlevi</span><span class="sxs-lookup"><span data-stu-id="72349-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="72349-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="72349-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="72349-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72349-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72349-105">Hamiltonian ile tutarlı bir zamana bağlı Oluşturucu sistemi döndürür `H(s) = 0` .</span><span class="sxs-lookup"><span data-stu-id="72349-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="72349-106">Çıkış: [Timedependentgeneratorsystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="72349-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="72349-107">Tüm $s $ için Hamiltonian $H = $0 altında gelişleri temsil eden zamana bağlı Oluşturucu sistemi.</span><span class="sxs-lookup"><span data-stu-id="72349-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>