---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835391"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="2e99b-102">MeasurementOperators işlevi</span><span class="sxs-lookup"><span data-stu-id="2e99b-102">MeasurementOperators function</span></span>

<span data-ttu-id="2e99b-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="2e99b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="2e99b-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2e99b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2e99b-105">Bir Jordan-Wigner teriminin beklentisini hesaplamak için gereken tüm ölçüm işleçlerini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="2e99b-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="2e99b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2e99b-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="2e99b-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e99b-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e99b-108">Molesel sistemin benzetimini yapmak için gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="2e99b-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="2e99b-109">dizinler: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2e99b-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2e99b-110">Qubit her Pauli işlecinin dizinlerini içeren bir dizi öğesine uygulanır.</span><span class="sxs-lookup"><span data-stu-id="2e99b-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="2e99b-111">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2e99b-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2e99b-112">Jordan-Wigner teriminin türü.</span><span class="sxs-lookup"><span data-stu-id="2e99b-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="2e99b-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="2e99b-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="2e99b-114">Ölçüm işleçleri dizisi (her biri Pauli dizisi olmak üzere).</span><span class="sxs-lookup"><span data-stu-id="2e99b-114">An array of measurement operators (each being an array of Pauli).</span></span>