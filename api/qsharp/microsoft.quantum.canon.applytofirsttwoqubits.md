---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841360"
---
# <a name="applytofirsttwoqubits-operation"></a><span data-ttu-id="3f5dd-102">ApplyToFirstTwoQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="3f5dd-102">ApplyToFirstTwoQubits operation</span></span>

<span data-ttu-id="3f5dd-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3f5dd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3f5dd-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f5dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f5dd-105">Kayıttaki ilk iki qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="3f5dd-105">Applies an operation to the first two qubits in the register.</span></span>

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3f5dd-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3f5dd-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="3f5dd-107">Op: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f5dd-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3f5dd-108">İlk iki qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="3f5dd-108">An operation to be applied to the first two qubits</span></span>


### <a name="register--qubit"></a><span data-ttu-id="3f5dd-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3f5dd-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3f5dd-110">İşlemin uygulandığı ilk iki qubit için qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="3f5dd-110">Qubit array to the first two qubits of which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3f5dd-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f5dd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3f5dd-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3f5dd-112">Remarks</span></span>

<span data-ttu-id="3f5dd-113">Bu eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3f5dd-113">This is equivalent to:</span></span>

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a><span data-ttu-id="3f5dd-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3f5dd-114">See Also</span></span>

- [<span data-ttu-id="3f5dd-115">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsA</span><span class="sxs-lookup"><span data-stu-id="3f5dd-115">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [<span data-ttu-id="3f5dd-116">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsC</span><span class="sxs-lookup"><span data-stu-id="3f5dd-116">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [<span data-ttu-id="3f5dd-117">Microsoft. hisse. Canon. ApplyToFirstTwoQubitsCA</span><span class="sxs-lookup"><span data-stu-id="3f5dd-117">Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)