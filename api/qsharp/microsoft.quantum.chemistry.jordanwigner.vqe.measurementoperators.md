---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727632"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="210c1-102">MeasurementOperators işlevi</span><span class="sxs-lookup"><span data-stu-id="210c1-102">MeasurementOperators function</span></span>

<span data-ttu-id="210c1-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="210c1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="210c1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="210c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="210c1-105">Bir Jordan-Wigner teriminin beklentisini hesaplamak için gereken tüm ölçüm işleçlerini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="210c1-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="210c1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="210c1-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="210c1-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="210c1-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="210c1-108">Molesel sistemin benzetimini yapmak için gereken qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="210c1-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="210c1-109">dizinler: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="210c1-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="210c1-110">Qubit her Pauli işlecinin dizinlerini içeren bir dizi öğesine uygulanır.</span><span class="sxs-lookup"><span data-stu-id="210c1-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="210c1-111">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="210c1-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="210c1-112">Jordan-Wigner teriminin türü.</span><span class="sxs-lookup"><span data-stu-id="210c1-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="210c1-113">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="210c1-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="210c1-114">Ölçüm işleçleri dizisi (her biri Pauli dizisi olmak üzere).</span><span class="sxs-lookup"><span data-stu-id="210c1-114">An array of measurement operators (each being an array of Pauli).</span></span>