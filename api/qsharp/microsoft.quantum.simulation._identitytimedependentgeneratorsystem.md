---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726353"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="91aba-102">_IdentityTimeDependentGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="91aba-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="91aba-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="91aba-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="91aba-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91aba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91aba-105">`H(s) = 0`Bir zamanlama parametresi olduğu Hamiltonian ile tutarlı bir Oluşturucu sistemi döndürür `s` .</span><span class="sxs-lookup"><span data-stu-id="91aba-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="91aba-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="91aba-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="91aba-107">zamanlama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="91aba-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="91aba-108">Bu giriş yok sayılır ve <xref:microsoft.quantum.canon.timedependentgeneratorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="91aba-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="91aba-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="91aba-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="91aba-110">Tüm $s $ için Hamiltonian $H = $0 altında gelişleri temsil eden bir Oluşturucu sistemi.</span><span class="sxs-lookup"><span data-stu-id="91aba-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>