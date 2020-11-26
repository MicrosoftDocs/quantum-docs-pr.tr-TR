---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: Tartıtonepaulis işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 904c606393131d51eaa44d464ad52bec509eaf72
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204547"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="387b2-102">Tartıtonepaulis işlevi</span><span class="sxs-lookup"><span data-stu-id="387b2-102">WeightOnePaulis function</span></span>

<span data-ttu-id="387b2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="387b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="387b2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="387b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="387b2-105">Verilen sayıda qubit üzerinde tüm ağırlık-1 Pauli işleçleri dizisini döndürür.</span><span class="sxs-lookup"><span data-stu-id="387b2-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="387b2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="387b2-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="387b2-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="387b2-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="387b2-108">Döndürülen Pauli işleçlerinin tanımlandığı qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="387b2-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="387b2-109">Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="387b2-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="387b2-110">Her biri uzunlukla dizi olarak temsil edilen Multi-qubit Pauli işleçleri dizisi `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="387b2-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>