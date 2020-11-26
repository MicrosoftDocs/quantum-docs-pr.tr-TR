---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: e4f1eb396efb390c7470ea2aaf5c3b5be60b8c1b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217416"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="ccffb-102">ApplyToFirstTwoQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="ccffb-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="ccffb-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ccffb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ccffb-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccffb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccffb-105">Kayıttaki ilk iki qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="ccffb-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ccffb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ccffb-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="ccffb-107">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccffb-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ccffb-108">İlk iki qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="ccffb-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="ccffb-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ccffb-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ccffb-110">İşlemin uygulandığı ilk iki qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="ccffb-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccffb-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccffb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ccffb-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ccffb-112">Remarks</span></span>

<span data-ttu-id="ccffb-113">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="ccffb-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="ccffb-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ccffb-114">See Also</span></span>

- [<span data-ttu-id="ccffb-115">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="ccffb-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="ccffb-116">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="ccffb-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="ccffb-117">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="ccffb-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)