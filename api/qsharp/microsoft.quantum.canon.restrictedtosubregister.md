---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: Kısıttedtosubregister işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: c5a6bbe16d2f6a317f6ed6f258077095465995f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840220"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="260e2-102">Kısıttedtosubregister işlevi</span><span class="sxs-lookup"><span data-stu-id="260e2-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="260e2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="260e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="260e2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="260e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="260e2-105">Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="260e2-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="260e2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="260e2-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="260e2-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="260e2-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="260e2-108">Bir alt kayıt ile kısıtlanması için işlem.</span><span class="sxs-lookup"><span data-stu-id="260e2-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="260e2-109">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="260e2-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="260e2-110">İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="260e2-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="260e2-111">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="260e2-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="260e2-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="260e2-112">See Also</span></span>

- [<span data-ttu-id="260e2-113">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregistera</span><span class="sxs-lookup"><span data-stu-id="260e2-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="260e2-114">Microsoft. hisse. Canon. Kısıttedtosubregisterc</span><span class="sxs-lookup"><span data-stu-id="260e2-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="260e2-115">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregisterca</span><span class="sxs-lookup"><span data-stu-id="260e2-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)