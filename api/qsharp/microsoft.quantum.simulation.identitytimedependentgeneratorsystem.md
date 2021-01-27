---
uid: Microsoft.Quantum.Simulation.IdentityTimeDependentGeneratorSystem
title: Identitytimedependentgeneratorsystem işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.
ms.openlocfilehash: e25e01a1f16182ea55fabd325d200c8489df5953
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846795"
---
# <a name="identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="6eb55-102">Identitytimedependentgeneratorsystem işlevi</span><span class="sxs-lookup"><span data-stu-id="6eb55-102">IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="6eb55-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6eb55-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6eb55-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6eb55-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6eb55-105">Hamiltonian ile tutarlı bir zamana bağlı Oluşturucu sistemi döndürür `H(s) = 0` .</span><span class="sxs-lookup"><span data-stu-id="6eb55-105">Returns a time-dependent generator system consistent with the Hamiltonian `H(s) = 0`.</span></span>

```qsharp
function IdentityTimeDependentGeneratorSystem () : Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
```


## <a name="output--timedependentgeneratorsystem"></a><span data-ttu-id="6eb55-106">Çıkış: [Timedependentgeneratorsystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="6eb55-106">Output : [TimeDependentGeneratorSystem](xref:Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem)</span></span>

<span data-ttu-id="6eb55-107">Tüm $s $ için Hamiltonian $H = $0 altında gelişleri temsil eden zamana bağlı Oluşturucu sistemi.</span><span class="sxs-lookup"><span data-stu-id="6eb55-107">A time dependent generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>