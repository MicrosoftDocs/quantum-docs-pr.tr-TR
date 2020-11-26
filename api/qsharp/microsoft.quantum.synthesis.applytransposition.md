---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203323"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="0656e-102">ApplyTransposition işlemi</span><span class="sxs-lookup"><span data-stu-id="0656e-102">ApplyTransposition operation</span></span>

<span data-ttu-id="0656e-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0656e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0656e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0656e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="0656e-105">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0656e-105">Description</span></span>

<span data-ttu-id="0656e-106">Bu işlem, dizin üzerindeki genonu, `a` `b` belirtilen eyalet- `register` $n $ uzunluğundaki vektörde bulunan dizindeki genlerle değiştirir.</span><span class="sxs-lookup"><span data-stu-id="0656e-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="0656e-107">`a`Eşitse `b` , eyalet vektörü değiştirilmez.</span><span class="sxs-lookup"><span data-stu-id="0656e-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="0656e-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="0656e-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0656e-109">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0656e-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0656e-110">İlk dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="0656e-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="0656e-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0656e-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0656e-112">İkinci dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="0656e-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="0656e-113">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="0656e-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="0656e-114">Transkonumun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="0656e-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0656e-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0656e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

