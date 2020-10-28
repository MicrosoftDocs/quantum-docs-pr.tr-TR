---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerBlockEncodingGeneratorSystem
title: JordanWignerBlockEncodingGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 68693465aeb030abbc514dacb789c234901fe120
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727823"
---
# <a name="jordanwignerblockencodinggeneratorsystem-function"></a><span data-ttu-id="73304-102">JordanWignerBlockEncodingGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="73304-102">JordanWignerBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="73304-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="73304-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="73304-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73304-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73304-105">Tarafından tanımlanan bir Hamiltonian `JWOptimizedHTerms` `GeneratorSystem` ' i Pauli bakımından ifade olarak dönüştürür `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="73304-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function JordanWignerBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="73304-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="73304-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="73304-107">veri: [Jwoptimizedhterms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="73304-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="73304-108">Biçimdeki Hamiltonian açıklaması `JWOptimizedHTerms` .</span><span class="sxs-lookup"><span data-stu-id="73304-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="73304-109">Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="73304-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="73304-110">Hamiltonian as gösterimi `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="73304-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>