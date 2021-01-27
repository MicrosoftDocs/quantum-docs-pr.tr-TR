---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterC
title: Kısıttedtosubregisterc işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterC
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: f44e9ea4d17dcadc6d3c64941529db819b7f9784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840216"
---
# <a name="restrictedtosubregisterc-function"></a><span data-ttu-id="94ba5-102">Kısıttedtosubregisterc işlevi</span><span class="sxs-lookup"><span data-stu-id="94ba5-102">RestrictedToSubregisterC function</span></span>

<span data-ttu-id="94ba5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="94ba5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="94ba5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94ba5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94ba5-105">Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="94ba5-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="94ba5-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="94ba5-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function RestrictedToSubregisterC (op : (Qubit[] => Unit is Ctl), idxs : Int[]) : (Qubit[] => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="94ba5-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="94ba5-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="94ba5-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="94ba5-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="94ba5-109">Bir alt kayıt ile kısıtlanması için işlem.</span><span class="sxs-lookup"><span data-stu-id="94ba5-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="94ba5-110">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="94ba5-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="94ba5-111">İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="94ba5-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-ctl"></a><span data-ttu-id="94ba5-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="94ba5-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="94ba5-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="94ba5-113">See Also</span></span>

- [<span data-ttu-id="94ba5-114">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister</span><span class="sxs-lookup"><span data-stu-id="94ba5-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)