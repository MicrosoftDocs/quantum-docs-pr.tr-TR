---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726390"
---
# <a name="jwoptimizedgeneratorsystem-function"></a><span data-ttu-id="3dce4-102">JWOptimizedGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="3dce4-102">JWOptimizedGeneratorSystem function</span></span>

<span data-ttu-id="3dce4-103">Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3dce4-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="3dce4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3dce4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3dce4-105">Tarafından açıklanan Hamiltonian `JWOptimizedHTerms` 'yi `GeneratorSystem` , `GeneratorIndex` Bu dosyada tanımlanan kural açısından ifade edilen öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="3dce4-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3dce4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3dce4-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="3dce4-107">veri: [Jwoptimizedhterms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="3dce4-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="3dce4-108">Biçimdeki Hamiltonian açıklaması `JWOptimizedHTerms` .</span><span class="sxs-lookup"><span data-stu-id="3dce4-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="3dce4-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3dce4-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3dce4-110">Hamiltonian as gösterimi `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="3dce4-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>