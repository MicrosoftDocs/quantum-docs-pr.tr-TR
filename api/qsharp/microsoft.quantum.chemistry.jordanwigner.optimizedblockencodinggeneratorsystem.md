---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727727"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="e70a4-102">OptimizedBlockEncodingGeneratorSystem işlevi</span><span class="sxs-lookup"><span data-stu-id="e70a4-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="e70a4-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e70a4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e70a4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e70a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e70a4-105">Tarafından tanımlanan bir Hamiltonian `JWOptimizedHTerms` `GeneratorSystem` ' i Pauli bakımından ifade olarak dönüştürür `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e70a4-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="e70a4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e70a4-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="e70a4-107">veri: [Jwoptimizedhterms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="e70a4-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="e70a4-108">Biçimdeki Hamiltonian açıklaması `JWOptimizedHTerms` .</span><span class="sxs-lookup"><span data-stu-id="e70a4-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="e70a4-109">Çıkış: [Optimizedbegeneratorsystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="e70a4-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="e70a4-110">Hamiltonian as gösterimi `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="e70a4-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>