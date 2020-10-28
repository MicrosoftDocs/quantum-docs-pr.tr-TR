---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Oracletoayrık işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733359"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="0c2ce-102">Oracletoayrık işlevi</span><span class="sxs-lookup"><span data-stu-id="0c2ce-102">OracleToDiscrete function</span></span>

<span data-ttu-id="0c2ce-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0c2ce-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0c2ce-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c2ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c2ce-105">"Siyah kutu" Oracle 'ı temsil eden bir işlem verildiğinde, "siyah kutu" Oracle 'ın birden çok kez tekrarlandığı bir bağımsız Oracle döndürür.</span><span class="sxs-lookup"><span data-stu-id="0c2ce-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="0c2ce-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0c2ce-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="0c2ce-107">BlackICE. BlackICE: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="0c2ce-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="0c2ce-108">Üs olacak işlem.</span><span class="sxs-lookup"><span data-stu-id="0c2ce-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="0c2ce-109">Çıkış: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="0c2ce-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="0c2ce-110">Bir işlem, "siyah kutu" Oracle üzerinde kısmen uygulanmış ve ayrı zaman Oracle 'ı temsil eder</span><span class="sxs-lookup"><span data-stu-id="0c2ce-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>