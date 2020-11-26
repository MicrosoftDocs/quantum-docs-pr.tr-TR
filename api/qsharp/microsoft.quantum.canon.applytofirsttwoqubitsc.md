---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: ApplyToFirstTwoQubitsC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 6b6ee5f05ace92c15ce2038e2fedbaa2fee3dcc9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217365"
---
# <a name="applytofirsttwoqubitsc-operation"></a><span data-ttu-id="dbb59-102">ApplyToFirstTwoQubitsC işlemi</span><span class="sxs-lookup"><span data-stu-id="dbb59-102">ApplyToFirstTwoQubitsC operation</span></span>

<span data-ttu-id="dbb59-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dbb59-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dbb59-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbb59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbb59-105">Kayıttaki ilk iki qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="dbb59-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="dbb59-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="dbb59-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="dbb59-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="dbb59-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-ctl"></a><span data-ttu-id="dbb59-108">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="dbb59-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dbb59-109">İlk iki qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="dbb59-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="dbb59-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dbb59-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dbb59-111">İşlemin uygulandığı ilk iki qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="dbb59-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dbb59-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dbb59-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="dbb59-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="dbb59-113">Remarks</span></span>

<span data-ttu-id="dbb59-114">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="dbb59-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="dbb59-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dbb59-115">See Also</span></span>

- [<span data-ttu-id="dbb59-116">Microsoft. hisse. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="dbb59-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)