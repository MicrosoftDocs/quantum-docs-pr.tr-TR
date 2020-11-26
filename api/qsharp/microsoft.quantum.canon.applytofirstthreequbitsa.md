---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA
title: ApplyToFirstThreeQubitsA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: c3374ceba9f442f9315d4b5fc54b158327124926
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208780"
---
# <a name="applytofirstthreequbitsa-operation"></a><span data-ttu-id="3fc95-102">ApplyToFirstThreeQubitsA işlemi</span><span class="sxs-lookup"><span data-stu-id="3fc95-102">ApplyToFirstThreeQubitsA operation</span></span>

<span data-ttu-id="3fc95-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3fc95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3fc95-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fc95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fc95-105">Kayıttaki ilk üç qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="3fc95-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="3fc95-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3fc95-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsA (op : ((Qubit, Qubit, Qubit) => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="3fc95-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="3fc95-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-adj"></a><span data-ttu-id="3fc95-108">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="3fc95-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3fc95-109">İlk üç qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="3fc95-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3fc95-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3fc95-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3fc95-111">İşlemin uygulandığı ilk üç qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="3fc95-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3fc95-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fc95-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3fc95-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3fc95-113">Remarks</span></span>

<span data-ttu-id="3fc95-114">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3fc95-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="3fc95-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3fc95-115">See Also</span></span>

- [<span data-ttu-id="3fc95-116">Microsoft. hisse. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="3fc95-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)