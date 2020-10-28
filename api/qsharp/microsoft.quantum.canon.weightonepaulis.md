---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Tartıtonepaulis işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728285"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="8c99e-102">Tartıtonepaulis işlevi</span><span class="sxs-lookup"><span data-stu-id="8c99e-102">WeightOnePaulis function</span></span>

<span data-ttu-id="8c99e-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c99e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c99e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8c99e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8c99e-105">Verilen sayıda qubit üzerinde tüm ağırlık-1 Pauli işleçleri dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="8c99e-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="8c99e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8c99e-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="8c99e-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8c99e-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8c99e-108">Döndürülen Pauli işleçlerinin tanımlandığı qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="8c99e-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8c99e-109">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="8c99e-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="8c99e-110">Her biri uzunlukla dizi olarak temsil edilen Multi-qubit Pauli işleçleri dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="8c99e-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>