---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: ApplyToFirstTwoQubitsCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: a2281776b617d5c3f8cc706ea09d14995fce4a27
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208661"
---
# <a name="applytofirsttwoqubitsca-operation"></a><span data-ttu-id="e9fe8-102">ApplyToFirstTwoQubitsCA işlemi</span><span class="sxs-lookup"><span data-stu-id="e9fe8-102">ApplyToFirstTwoQubitsCA operation</span></span>

<span data-ttu-id="e9fe8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9fe8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9fe8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9fe8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9fe8-105">Kayıttaki ilk iki qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="e9fe8-105">Applies an operation to the first two qubits in the register.</span></span>
<span data-ttu-id="e9fe8-106">Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="e9fe8-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9fe8-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e9fe8-107">Input</span></span>

### <a name="op--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="e9fe8-108">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="e9fe8-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e9fe8-109">İlk iki qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="e9fe8-109">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e9fe8-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9fe8-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9fe8-111">İşlemin uygulandığı ilk iki qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="e9fe8-111">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9fe8-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9fe8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e9fe8-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e9fe8-113">Remarks</span></span>

<span data-ttu-id="e9fe8-114">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="e9fe8-114">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="e9fe8-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e9fe8-115">See Also</span></span>

- [<span data-ttu-id="e9fe8-116">Microsoft. hisse. Canon. ApplyToFirstTwoQubits</span><span class="sxs-lookup"><span data-stu-id="e9fe8-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubits</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)