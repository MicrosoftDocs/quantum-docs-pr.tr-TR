---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857994"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="a9cba-102">_IdentityTimeDependentGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="a9cba-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="a9cba-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="a9cba-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="a9cba-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9cba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9cba-105">`H(s) = 0`Bir zamanlama parametresi olduğu Hamiltonian ile tutarlı bir Oluşturucu sistemi döndürür `s` .</span><span class="sxs-lookup"><span data-stu-id="a9cba-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="a9cba-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a9cba-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="a9cba-107">zamanlama: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9cba-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a9cba-108">Bu giriş yok sayılır ve <xref:microsoft.quantum.canon.timedependentgeneratorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="a9cba-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="a9cba-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="a9cba-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="a9cba-110">Tüm $s $ için Hamiltonian $H = $0 altında gelişleri temsil eden bir Oluşturucu sistemi.</span><span class="sxs-lookup"><span data-stu-id="a9cba-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>