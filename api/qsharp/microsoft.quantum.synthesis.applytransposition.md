---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855575"
---
# <a name="applytransposition-operation"></a><span data-ttu-id="4ae75-102">ApplyTransposition işlemi</span><span class="sxs-lookup"><span data-stu-id="4ae75-102">ApplyTransposition operation</span></span>

<span data-ttu-id="4ae75-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="4ae75-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="4ae75-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ae75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4ae75-105">Description</span><span class="sxs-lookup"><span data-stu-id="4ae75-105">Description</span></span>

<span data-ttu-id="4ae75-106">Bu işlem, dizin üzerindeki genonu, `a` `b` belirtilen eyalet- `register` $n $ uzunluğundaki vektörde bulunan dizindeki genlerle değiştirir.</span><span class="sxs-lookup"><span data-stu-id="4ae75-106">This operation swaps the amplitude at index `a` with the amplitude at index `b` in the given state-vector of `register` of length $n$.</span></span>  <span data-ttu-id="4ae75-107">`a`Eşitse `b` , eyalet vektörü değiştirilmez.</span><span class="sxs-lookup"><span data-stu-id="4ae75-107">If `a` equals `b`, the state-vector is not changed.</span></span>

## <a name="input"></a><span data-ttu-id="4ae75-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="4ae75-108">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="4ae75-109">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4ae75-109">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4ae75-110">İlk dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="4ae75-110">First index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="b--int"></a><span data-ttu-id="4ae75-111">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4ae75-111">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4ae75-112">İkinci dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)</span><span class="sxs-lookup"><span data-stu-id="4ae75-112">Second index (must be a value from 0 to $2^n - 1$)</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="4ae75-113">qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4ae75-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4ae75-114">Transkonumun uygulandığı $n $ qubits listesi.</span><span class="sxs-lookup"><span data-stu-id="4ae75-114">A list of $n$ qubits to which the transposition is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ae75-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ae75-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="4ae75-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="4ae75-116">Example</span></span>

<span data-ttu-id="4ae75-117">2 qubitlerde $ | 1 \ Rangle $, $ | 2 \ Rangle $ ve $ | 3 \ Rangle $ sayı durumlarıyla ilgili Tekdüzen üst konumunu hazırlayın.</span><span class="sxs-lookup"><span data-stu-id="4ae75-117">Prepare a uniform superposition of number states $|1\rangle$, $|2\rangle$, and $|3\rangle$ on 2 qubits.</span></span>

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```