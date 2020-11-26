---
uid: Microsoft.Quantum.Canon.RestrictedToSubregisterA
title: Kısıttedtosubregistera işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregisterA
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 28128641a95c6948b5fa5730bf3bd90aa6bb1ef5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205295"
---
# <a name="restrictedtosubregistera-function"></a><span data-ttu-id="2f626-102">Kısıttedtosubregistera işlevi</span><span class="sxs-lookup"><span data-stu-id="2f626-102">RestrictedToSubregisterA function</span></span>

<span data-ttu-id="2f626-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2f626-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2f626-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f626-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f626-105">Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="2f626-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>
<span data-ttu-id="2f626-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="2f626-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function RestrictedToSubregisterA (op : (Qubit[] => Unit is Adj), idxs : Int[]) : (Qubit[] => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="2f626-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2f626-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="2f626-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="2f626-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2f626-109">Bir alt kayıt ile kısıtlanması için işlem.</span><span class="sxs-lookup"><span data-stu-id="2f626-109">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="2f626-110">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f626-110">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f626-111">İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="2f626-111">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit--is-adj"></a><span data-ttu-id="2f626-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="2f626-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>



## <a name="see-also"></a><span data-ttu-id="2f626-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="2f626-113">See Also</span></span>

- [<span data-ttu-id="2f626-114">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregister</span><span class="sxs-lookup"><span data-stu-id="2f626-114">Microsoft.Quantum.Canon.RestrictedToSubregister</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregister)