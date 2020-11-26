---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: cb6945f5aa398d0bf6417c5cfd21142008a54b13
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217453"
---
# <a name="applytofirstthreequbitsc-operation"></a><span data-ttu-id="491c8-102">ApplyToFirstThreeQubitsC işlemi</span><span class="sxs-lookup"><span data-stu-id="491c8-102">ApplyToFirstThreeQubitsC operation</span></span>

<span data-ttu-id="491c8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="491c8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="491c8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="491c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="491c8-105">Kayıttaki ilk üç qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="491c8-105">Applies an operation to the first three qubits in the register.</span></span>
<span data-ttu-id="491c8-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="491c8-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="491c8-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="491c8-107">Input</span></span>

### <a name="op--qubitqubitqubit--unit--is-ctl"></a><span data-ttu-id="491c8-108">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="491c8-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="491c8-109">İlk üç qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="491c8-109">An operation to be applied to the first three qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="491c8-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="491c8-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="491c8-111">İşlemin uygulandığı ilk üç qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="491c8-111">Qubit array to the first three qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="491c8-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="491c8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="491c8-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="491c8-113">Remarks</span></span>

<span data-ttu-id="491c8-114">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="491c8-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a><span data-ttu-id="491c8-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="491c8-115">See Also</span></span>

- [<span data-ttu-id="491c8-116">Microsoft. hisse. Canon. ApplyToFirstThreeQubits</span><span class="sxs-lookup"><span data-stu-id="491c8-116">Microsoft.Quantum.Canon.ApplyToFirstThreeQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)