---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Oracletoayrık işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193854"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="a455d-102">Oracletoayrık işlevi</span><span class="sxs-lookup"><span data-stu-id="a455d-102">OracleToDiscrete function</span></span>

<span data-ttu-id="a455d-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a455d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a455d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a455d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a455d-105">"Siyah kutu" Oracle 'ı temsil eden bir işlem verildiğinde, "siyah kutu" Oracle 'ın birden çok kez tekrarlandığı bir bağımsız Oracle döndürür.</span><span class="sxs-lookup"><span data-stu-id="a455d-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="a455d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a455d-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="a455d-107">BlackICE + CTL 'de kara Boxoracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a455d-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a455d-108">Üs olacak işlem.</span><span class="sxs-lookup"><span data-stu-id="a455d-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="a455d-109">Çıkış: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="a455d-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="a455d-110">Bir işlem, "siyah kutu" Oracle üzerinde kısmen uygulanmış ve ayrı zaman Oracle 'ı temsil eder</span><span class="sxs-lookup"><span data-stu-id="a455d-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>