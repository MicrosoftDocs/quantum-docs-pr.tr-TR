---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830905"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="ccd45-102">AllowAtMostNQubits işlemi</span><span class="sxs-lookup"><span data-stu-id="ccd45-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="ccd45-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ccd45-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ccd45-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ccd45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ccd45-105">Bu işleme ve adeklem çağrısı arasında, using deyimleri ile verilen sayıda ek qubit için en fazla bir kaç sayının ayrıldığını onaylar.</span><span class="sxs-lookup"><span data-stu-id="ccd45-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ccd45-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ccd45-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="ccd45-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ccd45-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ccd45-108">Ayrılabilen en fazla qubit sayısı.</span><span class="sxs-lookup"><span data-stu-id="ccd45-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="ccd45-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ccd45-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ccd45-110">Hata durumunda görüntülenecek bir ileti.</span><span class="sxs-lookup"><span data-stu-id="ccd45-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ccd45-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ccd45-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="ccd45-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="ccd45-112">Example</span></span>

<span data-ttu-id="ccd45-113">Aşağıdaki kod parçacığı, bu tanılamayı destekleyen makinelerde yürütüldüğünde başarısız olur:</span><span class="sxs-lookup"><span data-stu-id="ccd45-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="ccd45-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ccd45-114">Remarks</span></span>

<span data-ttu-id="ccd45-115">Bu işlem, onu desteklemeyen hedefler üzerinde bir işleç ile değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="ccd45-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>