---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733938"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="5ddda-102">ApplyTransposition işlemi</span><span class="sxs-lookup"><span data-stu-id="5ddda-102">ApplyTransposition operation</span></span>

<span data-ttu-id="5ddda-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5ddda-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5ddda-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5ddda-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="5ddda-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="5ddda-105">Description</span></span>

<span data-ttu-id="5ddda-106">Bu işlem, dizin üzerindeki genonu, `a` `b` belirtilen eyalet- `register` $n $ uzunluğundaki vektörde bulunan dizindeki genlerle değiştirir.</span><span class="sxs-lookup"><span data-stu-id="5ddda-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="5ddda-107">`a`Eşitse `b` , eyalet vektörü değiştirilmez.</span><span class="sxs-lookup"><span data-stu-id="5ddda-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="5ddda-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="5ddda-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5ddda-109">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ddda-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ddda-110">İlk dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="5ddda-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="5ddda-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ddda-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ddda-112">İkinci dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="5ddda-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5ddda-113">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5ddda-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5ddda-114">Transkonumun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="5ddda-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5ddda-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5ddda-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

