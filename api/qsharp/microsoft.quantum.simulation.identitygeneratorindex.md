---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Identitygeneratorındex işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733527"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="2d20a-102">Identitygeneratorındex işlevi</span><span class="sxs-lookup"><span data-stu-id="2d20a-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="2d20a-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="2d20a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="2d20a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d20a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d20a-105">Identity evrimu işlemine karşılık gelen sıfır Hamiltonian ile tutarlı bir Oluşturucu dizini döndürür `H = 0` .</span><span class="sxs-lookup"><span data-stu-id="2d20a-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="2d20a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2d20a-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="2d20a-107">ıdxterm: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2d20a-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2d20a-108">Bu giriş yok sayılır ve <xref:microsoft.quantum.simulation.generatorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="2d20a-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="2d20a-109">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2d20a-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2d20a-110">Hamiltonian $H = $0 altında evrimi temsil eden bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="2d20a-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>