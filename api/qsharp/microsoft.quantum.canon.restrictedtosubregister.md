---
uid: Microsoft.Quantum.Canon.RestrictedToSubregister
title: Kısıttedtosubregister işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RestrictedToSubregister
qsharp.summary: Restricts an operation to an array of indices of a register, i.e., a subregister.
ms.openlocfilehash: a49b15ac9c3ba9c1959bdead11549c1f37caabf9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205380"
---
# <a name="restrictedtosubregister-function"></a><span data-ttu-id="71d74-102">Kısıttedtosubregister işlevi</span><span class="sxs-lookup"><span data-stu-id="71d74-102">RestrictedToSubregister function</span></span>

<span data-ttu-id="71d74-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="71d74-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="71d74-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="71d74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="71d74-105">Bir işlemi, bir kaydın dizin dizini (örneğin, alt kayıt) ile kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="71d74-105">Restricts an operation to an array of indices of a register, i.e., a subregister.</span></span>

```qsharp
function RestrictedToSubregister (op : (Qubit[] => Unit), idxs : Int[]) : (Qubit[] => Unit)
```


## <a name="input"></a><span data-ttu-id="71d74-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="71d74-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="71d74-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71d74-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="71d74-108">Bir alt kayıt ile kısıtlanması için işlem.</span><span class="sxs-lookup"><span data-stu-id="71d74-108">Operation to be restricted to a subregister.</span></span>


### <a name="idxs--int"></a><span data-ttu-id="71d74-109">ıdxs: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="71d74-109">idxs : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="71d74-110">İşlemin hangi qubits 'e kısıtlanacağını gösteren dizin dizisi.</span><span class="sxs-lookup"><span data-stu-id="71d74-110">Array of indices, indicating to which qubits the operation will be restricted.</span></span>



## <a name="output--qubit--unit"></a><span data-ttu-id="71d74-111">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="71d74-111">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 



## <a name="see-also"></a><span data-ttu-id="71d74-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="71d74-112">See Also</span></span>

- [<span data-ttu-id="71d74-113">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregistera</span><span class="sxs-lookup"><span data-stu-id="71d74-113">Microsoft.Quantum.Canon.RestrictedToSubregisterA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterA)
- [<span data-ttu-id="71d74-114">Microsoft. hisse. Canon. Kısıttedtosubregisterc</span><span class="sxs-lookup"><span data-stu-id="71d74-114">Microsoft.Quantum.Canon.RestrictedToSubregisterC</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterC)
- [<span data-ttu-id="71d74-115">Microsoft. hisse. Canon. kısıtlayıcı Tedtosubregisterca</span><span class="sxs-lookup"><span data-stu-id="71d74-115">Microsoft.Quantum.Canon.RestrictedToSubregisterCA</span></span>](xref:Microsoft.Quantum.Canon.RestrictedToSubregisterCA)