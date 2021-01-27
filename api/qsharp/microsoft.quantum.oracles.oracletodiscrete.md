---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: Oracletoayrık işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842530"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="9403e-102">Oracletoayrık işlevi</span><span class="sxs-lookup"><span data-stu-id="9403e-102">OracleToDiscrete function</span></span>

<span data-ttu-id="9403e-103">Ad alanı: [Microsoft. hisse. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9403e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9403e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9403e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9403e-105">"Siyah kutu" Oracle 'ı temsil eden bir işlem verildiğinde, "siyah kutu" Oracle 'ın birden çok kez tekrarlandığı bir bağımsız Oracle döndürür.</span><span class="sxs-lookup"><span data-stu-id="9403e-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="9403e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9403e-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="9403e-107">BlackICE + CTL 'de kara Boxoracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9403e-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9403e-108">Üs olacak işlem.</span><span class="sxs-lookup"><span data-stu-id="9403e-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="9403e-109">Çıkış: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="9403e-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="9403e-110">Bir işlem, "siyah kutu" Oracle üzerinde kısmen uygulanmış ve ayrı zaman Oracle 'ı temsil eder</span><span class="sxs-lookup"><span data-stu-id="9403e-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="9403e-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="9403e-111">Example</span></span>

<span data-ttu-id="9403e-112">`OracleToDiscrete(U)(3, target)``U(target)`tekrararda üç kez eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="9403e-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>