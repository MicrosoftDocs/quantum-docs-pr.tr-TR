---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727764"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="25ae8-102">JordanWignerGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="25ae8-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="25ae8-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="25ae8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="25ae8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25ae8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25ae8-105">Tarafından açıklanan Hamiltonian `JWOptimizedHTerms` 'yi `GeneratorSystem` , `GeneratorIndex` Bu dosyada tanımlanan kural açısından ifade edilen öğesine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="25ae8-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="25ae8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="25ae8-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="25ae8-107">veri: [Jwoptimizedhterms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="25ae8-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="25ae8-108">Biçimdeki Hamiltonian açıklaması `JWOptimizedHTerms` .</span><span class="sxs-lookup"><span data-stu-id="25ae8-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="25ae8-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="25ae8-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="25ae8-110">Hamiltonian as gösterimi `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="25ae8-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>