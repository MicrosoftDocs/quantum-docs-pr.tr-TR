---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Identitygeneratorındex işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844332"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="77bfe-102">Identitygeneratorındex işlevi</span><span class="sxs-lookup"><span data-stu-id="77bfe-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="77bfe-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="77bfe-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="77bfe-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77bfe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77bfe-105">Identity evrimu işlemine karşılık gelen sıfır Hamiltonian ile tutarlı bir Oluşturucu dizini döndürür `H = 0` .</span><span class="sxs-lookup"><span data-stu-id="77bfe-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="77bfe-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="77bfe-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="77bfe-107">ıdxterm: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77bfe-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77bfe-108">Bu giriş yok sayılır ve <xref:microsoft.quantum.simulation.generatorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="77bfe-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="77bfe-109">Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="77bfe-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="77bfe-110">Hamiltonian $H = $0 altında evrimi temsil eden bir Oluşturucu dizini.</span><span class="sxs-lookup"><span data-stu-id="77bfe-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>