---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 5572bd2a096a4f9bdb1153ae80950ae854965b82
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217467"
---
# <a name="applytofirstthreequbits-operation"></a><span data-ttu-id="788b2-102">ApplyToFirstThreeQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="788b2-102">ApplyToFirstThreeQubits operation</span></span>

<span data-ttu-id="788b2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="788b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="788b2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="788b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="788b2-105">Kayıttaki ilk üç qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="788b2-105">Applies an operation to the first three qubits in the register.</span></span>

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="788b2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="788b2-106">Input</span></span>

### <a name="op--qubitqubitqubit--unit"></a><span data-ttu-id="788b2-107">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="788b2-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="788b2-108">İlk üç qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="788b2-108">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="788b2-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="788b2-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="788b2-110">İşlemin uygulandığı ilk üç qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="788b2-110">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="788b2-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="788b2-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="788b2-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="788b2-112">Remarks</span></span>

<span data-ttu-id="788b2-113">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="788b2-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="788b2-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="788b2-114">See Also</span></span>

- [<span data-ttu-id="788b2-115">Microsoft. hisse. Canon. ApplyToFirstThreeQubitsC</span><span class="sxs-lookup"><span data-stu-id="788b2-115">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [<span data-ttu-id="788b2-116">Microsoft. hisse. Canon. ApplyToFirstThreeQubitsA</span><span class="sxs-lookup"><span data-stu-id="788b2-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [<span data-ttu-id="788b2-117">Microsoft. hisse. Canon. ApplyToFirstThreeQubitsCA</span><span class="sxs-lookup"><span data-stu-id="788b2-117">Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)